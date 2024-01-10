<template>
	<div id="tariffs" class="tariffs container">
		<h2 class="title">Тарифы</h2>
		<div class="tariffs__cards">
			<div v-for="(tarif, index) in tariffs" :key="index" class="card">
				<div class="info">
					<div class="info__title">
						<span v-show="tarif.extend">Расширенный</span>
						<span v-show="!tarif.extend">Стандартный</span>
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
							<p class="price__title">{{ item.title[1] }}</p>
						</div>
					</div>
				</div>
			</div>
		</div>
		<div class="order-btns">
			<button class="order-btn btn" @click="openOrderForm">
				Купить
			</button>
			<button class="order-btn btn" @click="openOrderForm">
				Купить
			</button>
		</div>
	</div>
</template>
<script>

export default {

	data() {
		return {
			tariffs: [
				{
					title: `Fin Flow #001`,
					text: [
						{ list: `Интерактивный отчёт`, sublist: [`ОФР`, `Банк и Касса`, `Кредиты и Займы`] },
						{ list: `Настройка отчёта в соответствии с учётной политикой`, },
						{ list: `Подключение к отчёту до 3-х компаний`, },
					],
					price: [
						{
							title: [`Стоимость за месяц`, `Бесплатный тестовый период 10 дней`],
							price: [`8 000 руб.`],
						},
					],
					extend: false,
				},
				{
					title: `Fin Flow #002`,
					text: [
						{ list: `Интерактивный отчёт`, sublist: [`ОФР`, `ОДДС`, `Банк и Касса`, `Кредиты и Займы`] },
						{ list: `Настройка отчёта в соответствии с учётной политикой`, },
						{ list: `Подключение к отчёту до 3-х компаний`, },
					],
					price: [
						{
							title: [`Стоимость за месяц`, `Бесплатный тестовый период 10 дней`],
							price: [`10 000 руб.`],
						},
					],
					extend: true
				}],
			open: false,
			modalWindowList: [
				{ link: "https://t.me/galaxyflowofficial", socialMedia: "Telegram", linkText: "telegram@galaxyflowofficial" },
				{ link: "viber://chat?number=+79225201900", socialMedia: "Viber", linkText: "viber@galaxyflowofficial" },
				{ link: "https://wa.me/79225201900", socialMedia: "Whatsapp", linkText: "whatsapp@galaxyflowofficial" },
				{ link: "mailto:element-global18@yandex.ru", socialMedia: "Email", linkText: "element-global18@yandex.ru" },
			]
		}
	},
	methods: {
		openOrderForm() {
			window.open("https://yandex.ru/business/widget/request/company/134561867869", "_blank", `width=${window.innerWidth / 2}, height=${window.innerHeight / 1.2}, top=${window.innerHeight / 10}, left=${window.innerWidth / 4}`);
		}
	},
}
</script>
<style lang="sass">
.tariffs__cards
	display: flex
	height: 100%
	flex-direction: row
	align-items: center
	justify-content: space-around
	overflow: hidden
	.card
		display: flex
		height: 565px
		min-width: 30%
		max-width: 30%
		border-radius: 30px
		border: 2px solid #000
		background: #ABBED7
		box-shadow: 3px 3px 20px 0px rgba(0, 0, 0, 0.10)
		padding: 10px 10px
		@media screen and (max-width: 1200px)
			min-width: 40%
		@media screen and (max-width: 800px)
			min-width: 30%
		.info__list
			max-height: 25%
			max-width: 100%
			padding-bottom: 10px
		p,h3,li
			color: #FFF
			font-size: 25px
			line-height: 25px
			padding-top: 5px
			@media screen and (max-width: 1500px)
				font-size: 20px
				padding-top: 14px
				line-height: 20px
			@media screen and (max-width: 800px)
				font-size: 1.2em
				padding-top: 0
				line-height: 20.5px
				.sub-list
					li
						font-size: 0.85em
		h3,p
			text-align: center
		.info__title
			padding-top: 0px
		.price__title
			@media screen and (max-width: 800px)
				padding-top: 10px

	.card ~ .card
		background: #FFF
		.info__list
			padding-bottom: 8px
		.info__title
			padding-top: 0px
		p,h3,li
			font-size: 27px
			color: #6E6E73
			@media screen and (max-width: 1580px)
				font-size: 20px
				padding-top: 14px
				line-height: 20px
				.sub-list
					li
						font-size: 1em
						line-height: 20px
						padding-top: 15px
			@media screen and (max-width: 1500px)
				font-size: 20px
				padding-top: 14px
				line-height: 20px
				.sub-list
					li
						font-size: 1em
						line-height: 20px
						padding-top: 10px
			@media screen and (max-width: 1200px)
				font-size: 20px
				padding-top: 15.5px
				line-height: 20px
				.sub-list
					li
						font-size: 1em
						line-height: 20px
						padding-top: 10px
			@media screen and (max-width: 800px)
				font-size: 1.2em
				padding-top: 0
				line-height: 18.8px
				.sub-list
					li
						font-size: 0.85em
						padding-top: 2px
		.price__title
			@media screen and (max-width: 800px)
				padding-top: 10px
	span
		margin-left: 50%
		font-size: 1.5em
		background: #E30000
		color: white
		border-radius: 30px
		padding: 0 10px
		@media screen and (max-width: 1700px)
			margin-left: 45%
			padding: 0 10px
			font-size: 1em
		@media screen and (max-width: 1400px)
			margin-left: 45%
			padding: 0 10px
			font-size: 1em
		@media screen and (max-width: 1200px)
			margin-left: 50%
			padding: 0 10px
			font-size: 0.75em
		@media screen and (max-width: 800px)
			margin-left: 50%
			padding: 0 10px
			font-size: 0.75em
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
.order-btns,.modal-btn
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
		font-size: 1.2em
		line-height: 20px
	li::before
		content: "- "
</style>