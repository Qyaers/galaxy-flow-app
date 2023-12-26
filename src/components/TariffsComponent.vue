<template>
	<div id="tariffs" class="tariffs container">
		<h2 class="title">Тарифы</h2>
		<div class="tariffs__cards">
			<div v-for="(tarif, index) in tariffs" :key="index" class="card">
				<div class="info">
					<div class="info__title">
						<span v-show="tarif.extend" style="font-size: 15px;">Расширенный</span>
						<h3>{{ tarif.title }}</h3>
					</div>
					<ul v-for="(text, index) in tarif.text" :key="index" class="info__list">
						<li class="list-item">
							{{ text.list }}
							<ol class="sub-list">
								<li class="sub-list__item" v-for="(subitem, index) in text.sublist" :key="index">
									{{ subitem }}
								</li>
							</ol>
						</li>
					</ul>
					<div v-for="item in tarif.price" class="price-card">
						<div class="price-month">
							<p class="price__title">{{ item.title[0] }}</p>
							<p class="price__price">{{ item.price[0] }}</p>
						</div>
						<div class="price-year">
							<!-- <div v-show="!item.hasDiscount">
								<span>Скидка 20%</span>
							</div> -->
							<p class="price__title">{{ item.title[1] }}</p>
							<p class="price__price">{{ item.price[1] }}</p>
						</div>
					</div>
				</div>
			</div>
		</div>
		<div class="order-btns">
			<button class="order-btn btn" @click="open = true">
				Купить
			</button>
			<button class="order-btn btn" @click="open = true">
				Купить
			</button>
		</div>
	</div>
	<Teleport to="body">
		<div v-if="open" class="modal" @click.self="open = false">
			<div class="modal__window">
				<div class="modal__close-btn">
					<button class="close-btn" @click="open = false">X</button>
				</div>
				<div class="modal__content">
					<p>Для покупки нашего продукта свяжитесь с нами:</p>
					<ul class="modal__list" v-for="item in modalWindowList">
						<li class="modal__list-item">{{ item.socialMedia + ":" }} <a :href=item.link target="_blank">{{
							item.linkText }}</a>
						</li>
					</ul>
				</div>
			</div>
		</div>
	</Teleport>
</template>
<script>

export default {

	data() {
		return {
			tariffs: [
				{
					title: `#001`,
					text: [
						{ list: `Интерактивный отчёт`, sublist: [`ОФР`, `Банк и Касса`] },
						{ list: `Настройка отчёта в соответсвтии с учётом политики`, },
						{ list: `Подключение к отчёту до 3-х компаний`, },
					],
					price: [
						{
							title: [`Стоимость за месяц`, `Бесплатный тестовый период 10 дней`],
							price: [`8 000 руб.`],
							// hasDiscount: false,
						},
					],
					extend: false,
				},
				{
					title: `#002`,
					text: [
						{ list: `Интерактивный отчёт`, sublist: [`ОФР`, `Банк и Касса`, `ОДДС`] },
						{ list: `Настройка отчёта в соответсвтии с учётом политики`, },
						{ list: `Подключение к отчёту до 3-х компаний`, },
					],
					price: [
						{
							title: [`Стоимость за месяц`, `Бесплатный тестовый период 10 дней`],
							price: [`10 000 руб.`],
							// hasDiscount: false,
						},
					],
					extend: true
				}],
			open: false,
			modalWindowList: [
				{ link: "https://t.me/galaxyflowofficial", socialMedia: "Telegram", linkText: "telegram@galaxyflowofficial" },
				{ link: "https://viber://chat?number=+79225201900", socialMedia: "Viber", linkText: "viber@galaxyflowofficial" },
				{ link: "https://wa.me/79225201900", socialMedia: "Whatsapp", linkText: "whatsapp@galaxyflowofficial" },
				{ link: "mailto:element-global18@yandex.ru", socialMedia: "Email", linkText: "element-global18@yandex.ru" },
			]
		}
	},
	methods: {
		isMobile() {
			if (/Android|webOS|iPhone|iPad|iPod|BlackBerry|BB|PlayBook|IEMobile|Windows Phone|Kindle|Silk|Opera Mini/i.test(navigator.userAgent)) {
				this.modalWindowList[1].link = "http://viber://chat?number=79225201900";
			} else {
				this.modalWindowList[1].link = "http://viber://chat?number=+79225201900";
			}
		}
	},
	mounted() {
		this.isMobile();
	},
}
</script>
<style lang="sass">
.tariffs__cards
	display: flex
	flex-direction: row
	align-items: center
	justify-content: space-around
	.card
		display: flex
		flex-wrap: wrap
		height: 60vh
		width: 22vw
		border-radius: 30px
		border: 2px solid #000
		background: #ABBED7
		box-shadow: 3px 3px 20px 0px rgba(0, 0, 0, 0.10)
		p,h3,li
			color: #FFF
			font-size: 27px
			line-height: 34px
		h3,p
			text-align: center
		.info__title
			padding-top: 16px
	.card ~ .card
		.info__title
			padding-top: 0px
		background: #FFF
		p,h3,li
			color: #6E6E73
			line-height: 30px
	span
		margin-left: 60%
		font-size: 21px
		background: #E30000
		color: white
		border-radius: 30px
		padding: 0 10px
	.price-year
		span
			margin-left: 50%
			font-size: 21px
			background: #E30000
			color: white
			border-radius: 30px
			padding: 0 10px
	.price-card
		border-top: 5px solid rgba(0, 0, 0, 0.45)
.order-btns
	margin: 2vh 0vh 2vh 0vh 
	display: flex
	flex-direction: row
	align-items: center
	justify-content: space-around
	button
		color: white
	button ~ button
		color: #6E6E71
		background: white
.sub-list
	padding-left: 0px
	li
		list-style-type: none
	li::before
		content: "- "
//modal window styles
.modal
	position: fixed
	top: 0
	height: 100%
	width: 100%
	z-index: 999
	background: rgba(0, 0, 0, 0.50)
	display: flex
	align-items: center
	justify-content: center
	ul,li
		color: #6E6E73
		text-indent: 0.5em
		font-size: 1.4em
		li a
			font-size: 1em
	.modal__window
		position: fixed
		display: flex
		flex-direction: column
		justify-content: space-between
		border-radius: 2em
		background: #F5F5F7
		width: 60%
		height: 50%
		.modal__close-btn
			position: absolute
			top: 4%
			right: 4%
			border: none
			.close-btn
				border: 1px solid white
				background: white
				border-radius: 20px
				font-size: 1.5em
				color: black
				&:hover
					background: rgba(0, 0, 0, 0.25)
		.modal__content
			width: 80%
			margin: 0 auto
			margin-top: 5%
</style>