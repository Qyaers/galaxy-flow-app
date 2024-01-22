<template>
	<div id="product" class="product container">
		<div class="product__title">
			<h2>Наш продукт</h2>
		</div>
		<video class="product__preview-vid" preload loop autoplay muted>
			<source src="../assets/mainView.mp4">
		</video>
		<div class="product__feat">
			<div class="feat__container" v-for="item in featchers" :key="index">
				<img class="feat__img" src="../assets/featImg.png" alt="иконка фичи">
				<div class="feat__text">
					<p>{{ item }}</p>
				</div>
			</div>
		</div>
		<div class="product__about">
			<productItemComponent v-for="(item, index) in productInfoItems" :item="item" :key="index"></productItemComponent>
		</div>
		<div class="product__requirements">
			<productRequirementsComponent :requirements="productRequirements">
			</productRequirementsComponent>
		</div>
		<div class="current-info-btns">
			<button v-for="tab in tabs" :class="['btn', { active: currentTab === tab.component }]"
				@click="changeComponent(tab.component)" :disabled="tab.disabledBtn">
				{{ tab.text }}
			</button>
		</div>
		<transition name="bounce">
			<component :is="currentTab"> </component>
		</transition>
		<div class="product__report-toogle" @click="toggleFinReport()">
			<h3 class="question-text">Пример финансового отчёта Fin Flow</h3>
			<p class="toggle-icon">
				{{ this.isOpen ? "—" : "＋" }}
			</p>

		</div>
		<div ref="product_report" class="product__report">
			<p>*если не загружается отчёт попробуйте переключить сеть с Wifi на мобильную или наоборот</p>
			<iframe class="report-view" title="Report Section"
				src="https://app.fabric.microsoft.com/view?r=eyJrIjoiYTdhMmQ1N2YtMTE4OC00NzFlLWI0ZDEtMjIyM2U1OTVmMWQ1IiwidCI6ImI4MmQ2N2FmLWJmMGQtNGJjOS04Y2QxLWE0ZWQwZTBlMzVjOSIsImMiOjl9&pageName=ReportSectioneb70caf7e92ea1477416"
				frameborder="0" allowFullScreen="true"></iframe>
		</div>
	</div>
</template>
<script>
import productItemComponent from '../components/ProductItem.vue';
import productRequirementsComponent from '../components/ProductRequirements.vue'
import ofrComponent from '../components/OFR.vue';
import oddcComponent from '../components/ODDC.vue';
import bankAndCashComponent from '../components/BankAndCash.vue';
import creditsAndLoansComponent from '../components/CreditsAndLoans.vue';

export default {
	components: {
		productItemComponent,
		productRequirementsComponent,
		ofrComponent,
		oddcComponent,
		bankAndCashComponent,
		creditsAndLoansComponent
	},
	data() {
		return {
			featchers: [
				"Принимайте ключевые решения на основе аналитики",
				"Финансы компании в единой форме",
				"Удобный  интерактивный отчёт"
			],
			productRequirements: [
				{
					title: "Условия подключения",
					info: ["1C Предприятие", "Бухгалтер", "Яндекс диск"]
				},
				{
					title: "Доступ с устройств",
					info: ["Компьютер", "Планшет", "Смартфон"]
				},
				{
					title: "Иходные данные",
					info: ["Оборотно-сальдовоые ведомости 1С", "Банковские выписки"]
				},
			],
			currentTab: "ofrComponent",
			tabs: [
				{ text: "ОФР", component: "ofrComponent", disabledBtn: true },
				{ text: "ОДДС", component: "oddcComponent", disabledBtn: false },
				{ text: "Банк и касса", component: "bankAndCashComponent", disabledBtn: false },
				{ text: "Кредиты и займы", component: "creditsAndLoansComponent", disabledBtn: false },
			],
			productInfoItems: [
				{
					title: "Особенности продукта",
					text: "Данные из 1С в интерактивном формате. Бесплатная настройка. Бесплатная поддержка",
					class: "item-direction",
					img: "img/Dashboard.png"
				},
				{
					title: "Консолидируй данные",
					text: "В отчёте можно объединить данные  по неограниченному количеству компаний",
					class: "item-direction-reverse",
					img: "img/Calculator.png"
				},
				{
					title: "Увеличь эффективность бизнеса",
					text: "Отслеживай финансовые показатели компании, контролируй банк и кассу, следи за кредитами и займами",
					class: "item-direction",
					img: "img/Data.png"
				},
				{
					title: "Защита информации",
					text: "На каждом этапе формирования отчёта ваша информация под защитой. Все файлы при передаче шифруются",
					class: "item-direction-reverse",
					img: "img/Protection.png"
				},
				{
					title: "Соответствие стандартам РСБУ",
					text: "Исходные данные для отчёта формируются в 1С Предприятие в соответствии с учётной политикой компании",
					class: "item-direction",
					img: "img/BD.png"
				},
			],
			disabledBtn: true,
			isOpen: false
		}
	},
	methods: {
		changeComponent(component) {
			for (const key in this.tabs) {
				if (this.tabs[key].component == component) {
					this.currentTab = component
					this.tabs[key].disabledBtn = !this.tabs[key].disabledBtn
				} else {
					if (this.tabs[key].disabledBtn) {
						this.tabs[key].disabledBtn = !this.tabs[key].disabledBtn
					}
				}
			}
		},
		toggleFinReport(itemClass) {
			let toogledItem = document.querySelectorAll(`.${itemClass}`)
			if (this.isOpen) {
				this.collapse();
			} else {
				this.expand();
			}
			this.isOpen = !this.isOpen
		},
		collapse() {
			const item = this.$refs.product_report;
			item.style.height = 0;
		},
		expand() {
			const item = this.$refs.product_report;
			item.style.height = 100 + "%";
		}
	},

}
</script>
<style lang="sass">
	.product__preview-vid
		height: 100%
		border-radius: 20px
		width: 100%
		padding: 0
		margin: 0 auto
		@media screen and (max-width: 1100px)
			width: 100%
	.product__feat,.feat__container
		display: flex
		flex-direction: row
		justify-content: space-around
		align-items: center
		padding: 10px
		p
			font-size: 1.1em
			text-align: center
	.product__about
		display: flex
		flex-direction: column
		justify-content: space-evenly
	.current-info-btns
		display: flex
		flex-direction: row
		justify-content: space-evenly
		.btn
			max-height: 15%
			min-height: 10%
			max-width: 22.5%
			@media screen and (max-width: 780px)
				font-size: 1em
			@media screen and (max-width: 400px)
				font-size: 1.15em

	.product__report-toogle
		display: flex
		flex-direction: row
		justify-content: space-between
		margin-top: 20px
		background: linear-gradient(100deg, rgba(255, 255, 255, 0.10) 0%, rgba(171, 190, 215, 0.10) 100%)
		box-shadow: 3px 3px 20px 0px rgba(0, 0, 0, 0.10)
		padding: 10px 0
		transition: transform 1s
		position: relative
		border-radius: 1em
		padding-left: 0.8vw
		cursor: pointer
		&:hover
			background: hsl(35 10% 30% / 0.15)
		&:active
			transform: translateY(4px)
			box-shadow: none
	.product__report
		transition: 0.25s
		height: 0
		overflow: hidden
		display: flex
		flex-direction: column
		text-align: justify
		justify-content: center
		align-items: center
		margin: 0 auto
		width: 100%
		p
			padding: 10px
		.report-view
			min-width: 100%
			min-height: 80vh
			box-shadow: 3px 3px 20px 0px rgba(0, 0, 0, 0.10)
			border-radius: 20px
			@media screen and (max-width: 800px)
				min-height: 60vh
				min-width: 100%
	.bounce-enter-active 
		animation: bounce-in 1.5s

	@keyframes bounce-in
		0%
			transform: scale(0)
		100% 
			transform: scale(1)
</style>