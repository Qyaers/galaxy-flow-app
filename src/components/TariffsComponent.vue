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
							<p class="card-price__title">{{ item.title[0] }}</p>
							<p class="card-price__title">{{ item.price[0] }}</p>
						</div>
						<div class="price-year">
							<div v-show="!item.hasDiscount">
								<span>Скидка 20%</span>
							</div>
							<p class="card-price__title">{{ item.title[1] }}</p>
							<p class="card-price__title">{{ item.price[1] }}</p>
						</div>
					</div>
				</div>
			</div>
		</div>
		<div class="order-btns">
			<button class="order-btn btn">
				Купить
			</button>
			<button class="order-btn btn">
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
					title: `#001`,
					text: [
						{ list: `Интерактивный отчёт`, sublist: [`ОФР`, `Банк и Касса`] },
						{ list: `Настройка отчёта в соответсвтии с учётом политики`, },
						{ list: `Подключение к отчёту до 3-х компаний`, },
					],
					price: [
						{
							title: [`Стоимость за месяц`, `Стоимость за год`],
							price: [`19 900 руб.`, `175 900 руб.`],
							hasDiscount: false,
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
							title: [`Стоимость за месяц`, `Стоимость за год`],
							price: [`19 900 руб.`, `175 900 руб.`],
							hasDiscount: false,
						},
					],
					extend: true
				}]
		}
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
		font-size: 32px
	button ~ button
		color: black
		background: white
		font-size: 32px
.sub-list
	padding-left: 0px
	li
		list-style-type: none
	li::before
		content: "- "
</style>