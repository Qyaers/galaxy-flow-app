<template>
	<div class="oddc-container container">
		<div class="main-info">
			<div class="main-info__text" v-for="item in mainInfo">
				<h3 class="block-title">
					{{ item.title }}
				</h3>
				<div class="block-text">
					<p class="text" v-for="(info, index) in item.info" :key="index">
						{{ info }}
					</p>
				</div>
			</div>
		</div>
		<div class="featchers-info">
			<div class="featchers-info__text" v-for="item in featchersInfo">
				<h3 class="block-title">
					{{ item.title }}
				</h3>
				<div class="block-text">
					<p class="text" v-for="(info, index) in item.info" :key="index">
						{{ info }}
					</p>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	data() {
		return {
			mainInfo: [
				{ title: "Требования", info: ["1C Предприятие", "7 Zip архиватор", "Яндекс диск"], },
				{ title: "Цель", info: ["Контроль денежного потока"] },
				{ title: "Исходные данные", info: ["Обратно-сальдовые ведомости 1C", "Банковские выписки"] },
				{ title: "Доступ к отчёту", info: ["C компьютера", "C планшета", "C телефона"] }],
			featchersInfo: [
				{ title: "Особенности", info: ["#Ежедневное обновление", "#Аналитика контрагентов", "#Сортировка контрагентов по прибыльности"], },
				{ title: "Фильтры", info: ["По компаниям", "По контрагентам", "По статьям движения денежных средств"] }
			]
		}
	},
}
</script>

<style lang="sass">
.oddc-container
	display: flex
	flex-direction: row
	min-width: 100%
	min-height: 50%
	justify-content: space-between
	align-items: flex-start
	@media screen and (max-width: 1000px)
		flex-direction: column
	.main-info
		display: flex
		flex-direction: row
		flex-wrap: wrap
		@media screen and (max-width: 1000px)
			justify-content: space-around
		.block-text
			display: flex
			flex-direction: column
			justify-content: space-between
			width: 325px
			height: 170px
			border-radius: 15px
			background: #FFF
			box-shadow: 3px 3px 20px 0px rgba(0, 0, 0, 0.10)
			margin-right: 19px
			padding-left: 10px
			.text
				color: #6E6E73
				font-family: Roboto,sans-serif
				font-size: 1.6em
				font-style: normal
				font-weight: 700
				text-align: left
				text-indent: 0
				padding-top: 10px
				@media screen and (max-width: 1000px)
					font-size: 1.4em
	.featchers-info
		display: flex
		flex-direction: row
		width: 100%
		@media screen and (max-width: 1000px)
			justify-content: space-around
		.block-text
			display: flex
			flex-direction: column
			justify-content: space-around
			width: 354px
			height: 406px
			background-color: white
			border-radius: 15px
			margin-right: 19px
			padding-left: 10px
			box-shadow: 3px 3px 20px 0px rgba(0, 0, 0, 0.10)
			@media screen and (max-width: 1000px)
				width: 325px
				height: 380px
			.text
				color: #6E6E73
				font-family: Roboto,sans-serif
				font-size: 1.6em
				font-style: normal
				font-weight: 700
				text-align: left
				text-indent: 0
				@media screen and (max-width: 1000px)
					font-size: 1.4em
</style>