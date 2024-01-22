<template>
	<div class="credits-and-loans-container">
		<video class="credits-and-loans__video" preload loop autoplay muted>
			<source src="../assets/creditsAndLoans.mp4">
		</video>
		<div class="credits-and-loans__info">
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
		</div>
	</div>
</template>

<script>
export default {
	data() {
		return {
			mainInfo: [
				{ title: "Описание", info: ["Отчёт по текущим кредитам и займам компании"] },
				{ title: "Особенности", info: ["Аналитика кредиторов", "Расчёт основного долга и процентов", "Сортировка договоров по остатку задолженности"] },
				{ title: "Детализация", info: ["По дате", "По компаниям", "По кредиторам", "По типу задолженности", "По структуре задолженности"] },
			]
		}
	},
}
</script>

<style lang="sass">
.credits-and-loans-container
	display: flex
	flex-direction: column
	justify-content: center
	align-items: center
.credits-and-loans__video
	height: 100%
	border-radius: 20px
	width: 100%
	padding: 0
	margin: 50px 0px 0px 0px
.credits-and-loans__info
	margin-top: 2vh
	width: 100%
	display: flex
	flex-direction: row
	justify-content: space-evenly
	align-items: center
	.main-info
		display: grid
		grid-template-columns: 1fr 1fr 1fr
		grid-column-gap: 20px
		margin: 0 auto
		.block-text
			display: flex
			flex-direction: column
			justify-content: space-between
			width: 100%
			height: 340px
			border-radius: 15px
			background: linear-gradient(100deg, rgba(255, 255, 255, 0.10) 0%, rgba(171, 190, 215, 0.10) 100%)
			box-shadow: 3px 3px 20px 0px rgba(0, 0, 0, 0.10)
			padding: 10px
			@media screen and (max-width: 1580px) 
				width: 100%
			@media screen and (max-width: 1300px) 
				width: 300px
			@media screen and (max-width: 1000px) 
				width: 240px
			.text
				font-size: 1.5em
				text-align: left
				@media screen and (max-width: 1480px)
					font-size: 1.4em
				@media screen and (max-width: 1300px)
					font-size: 1.25em
</style>