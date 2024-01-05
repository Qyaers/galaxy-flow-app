<template lang="">
	<div id="faq" class="faq__container container">
	<h2>FAQ</h2>
		<div class="faq" v-for="(faqItem, index) in faqItems" :key="index" :faq="faqItem">
			<div class="question" @click="toggleAnswer(index,faqItem)">
				<p class="question-text">{{ faqItem.q }}</p>
				<p class="toggle-icon">
					{{faqItem.isOpen ? "—" : "＋" }}
				</p>
			</div>
			<div class="answer" ref="answer">
				<p>{{ faqItem.a}}</p>
				<ul v-if="faqItem.hasOwnProperty('list')" v-for="item in faqItem.list">
					<li>
					{{item}}
					</li>
				</ul>
			</div>
		</div>
	</div>
</template>
<script>
export default {
	data() {
		return {
			faqItems: [
				{
					q: `Какие преимущества у отчёта по сравнению со стандартным бухгалтерским учётом?`,
					a:
						`Наш продукт позволяет объединить данные с 
						нескольких компаний в едином отчёте и предоставляет 
						возможность взаимодействовать с данными в интерактивном формате.`,
					isOpen: false
				},
				{
					q: `Безопасно ли передавать данные из 1С Предприятие?`,
					a:
						`Да. На каждом этапе вы передаёте шифрованный архив с исходными данными. Исходные данные передаются на наш локальный сервер.`
					,
				},
				{
					q: `Как происходит настройка отчёта и сколько она стоит?`,
					a:
						`Настройка отчёта бесплатная. Весь алгоритм следующий:`
					,
					list: [
						`Аналитик настраивает универсальные отчёты в 1С Предприятие в соответствии с учётной политикой компании`,
						`Аналитик консультирует бухгалтера как выгружать данные на наш локальный сервер`,
						`Вместе с бухгалтером производится тестирование системы`,
						`После тестирования предоставляется логин и пароль для доступа к отчёту`
					]
				},
				{
					q: `Сколько времени займёт настройка отчёта и как долго он обновляется?`,
					a:
						`Время настройки отчёта зависит от количества подключаемых компаний. Обычно это занимает 1-2 рабочих дня. Время с отправки исходных данных до получения отчёта зависит от размера исходных данных. В среднем отчёт обновляется за 15-30 минут.`
				},
				{
					q: `Какие сервисы нужны для настройки отчёта?`,
					list: [
						`1С Предприятие для выгрузки исходных данных`,
						`7 Zip архиватор для шифрования архивов`,
						`Яндекс Диск для отправки отчётов на сервер`
					]
				},
				{
					q: `Как работает бесплатный пробный период?`,
					a:
						`Во время тестового периода 
						вы получаете доступ к полноценной версии отчёта по тарифу #002. 
						Настройка отчёта бесплатная и соответствует стандартам для тарифа #002. 
						В любой момент вы можете отказаться от тестового периода. 
						По истечении 10 дней вы можете приобрести один из тарифов. При этом повторная настройка отчёта не потребуется.`
				},
				{
					q: `Как пользоваться отчётом?`,
					a:
						`Наш аналитик поможет вам освоить отчёт. 
						Для этого он свяжется с вами по видеосвязи и объяснит все особенности работы с отчётом.`
				},
				{
					q: `Сколько компаний можно подключить к отчёту?`,
					a:
						`По любому из тарифов можно подключить не больше 3-х компаний. Если вам нужно подключить ещё несколько компаний, то можно приобрести дополнительный тариф.`
				},
				{
					q: `Планируется ли расширение функционала отчёта?`,
					a:
						`Да. В дальнейшем будут выходить обновления для текущих тарифов. Расширение функционала будет бесплатным.`
				}
			],
		};
	},
	methods: {
		toggleAnswer(index, faqItem) {
			if (faqItem.isOpen) {
				this.collapse(index);
			} else {
				this.expand(index);
			}
			faqItem.isOpen = !faqItem.isOpen
		},
		collapse(index, faqItem) {
			const answer = this.$refs.answer[index];
			answer.style.height = 0;
		},
		expand(index, faqItem) {
			const answer = this.$refs.answer[index];
			answer.style.height = answer.scrollHeight + "px";
		}
	}
}
</script>
<style lang="sass">
.faq__container
	display: flex
	flex-direction: column
	flex-shrink: 0
	flex-wrap: wrap
/* style the FAQ section */
.faq
	display: flex
	flex-direction: column
	justify-content: space-between
	width: 100%
.question
	display: flex
	flex-direction: row
	justify-content: space-between
	margin-top: 20px
	background: hsl(35 10% 30% / 0.1)
	box-shadow: 0px 4px 0px 0 #88888855
	padding: 10px 0
	transition: transform 0.2s
	position: relative
	border-radius: 1em
	padding-left: 0.8vw
	cursor: pointer
	.question-text
		font-size: 1.5em
		text-transform: uppercase
		font-weight: bold
		@media screen and (max-width: 1680px)
			font-size: 1.25em
			padding: 10px	
		@media screen and (max-width: 1200px)
			font-size: 1em
			padding: 10px	
		@media screen and (max-width: 800px)
			font-size: 0.8em
			padding: 10px	
.question:hover
	background: hsl(35 10% 30% / 0.15)

.question:active
	transform: translateY(4px)
	box-shadow: none

.answer 
	transition: 0.25s // smooth slide-in */
	height: 0 // starts collapsed
	overflow: hidden
	text-align: justify
	p,ul,li,span
		color: #6E6E73
		list-style-type: disc
	p
		font-size: 1.25em
		padding: 0px 20px 0px 20px
		
		@media screen and (max-width: 1680px)
			font-size: 1.15em
			padding: 10px	
		@media screen and (max-width: 1200px)
			font-size: 1em
			padding: 10px	
		@media screen and (max-width: 800px)
			font-size: 0.8em
			padding: 10px	
	li
		font-size: 1.25em
		@media screen and (max-width: 1680px)
			font-size: 1.15em
		@media screen and (max-width: 1200px)
			font-size: 1em
		@media screen and (max-width: 800px)
			font-size: 0.8em
.toggle-icon
	font-size: 1.5em
	font-weight: bold
	display: inline-block
	line-height: 0.5
	color: #666
	margin-top: 15px
	padding-right: 20px
</style>