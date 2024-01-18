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
				{ title: "Фильтры", info: ["По дате", "По компаниям", "По контрагентам", "По статьям движения денежных средств"] }
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
	grid-column-gap: 30px
	margin-top: 5vh
	@media screen and (max-width: 1200px)
		flex-direction: column
	.main-info
		display: grid
		grid-template-columns: 2fr 2fr
		grid-column-gap: 20px
		margin: 0 auto
		@media screen and (max-width: 1000px)
			justify-content: space-around
		.block-text
			display: flex
			flex-direction: column
			justify-content: space-between
			width: 325px
			height: 174px
			border-radius: 15px
			background: #FFF
			box-shadow: 3px 3px 20px 0px rgba(0, 0, 0, 0.10)
			padding: 10px
			@media screen and (max-width: 1580px) 
				width: 100%
				height: 174px
			@media screen and (max-width: 1200px) 
				width: 325px
				height: 174px
			.text
				font-size: 1.6em
				text-align: left
				@media screen and (max-width: 1000px)
					font-size: 1.4em

	.featchers-info
		display: grid
		grid-template-columns: 1fr 1fr
		grid-column-gap: 20px
		margin: 0 auto
		@media screen and (max-width: 1000px)
			justify-content: space-around
		.block-text
			display: flex
			flex-direction: column
			justify-content: space-between
			width: 325px
			height: 406px
			border-radius: 15px
			background: #FFF
			box-shadow: 3px 3px 20px 0px rgba(0, 0, 0, 0.10)
			padding: 10px
			@media screen and (max-width: 1580px) 
				width: 100%
				height: 406px
			@media screen and (max-width: 1200px) 
				width: 325px
				height: 406px
			.text
				font-size: 1.6em
				text-align: left
				@media screen and (max-width: 1000px)
					font-size: 1.4em
</style>