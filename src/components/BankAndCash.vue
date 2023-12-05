<template>
	<div class="bank-and-cash-container container">
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
				{ title: "Требования", info: ["1C Предприятие", "Компьютер", "Yandex диск"], },
				{ title: "Цель", info: ["Мониторинг денежных средств в банках и кассе"] },
				{ title: "Исходные данные", info: ["Обратно-сальдовые ведомости 1C"] },
				{ title: "Доступ к отчёту", info: ["C компьютера", "C планшета", "C телефона"] }],
			featchersInfo: [
				{ title: "Особенности", info: ["#Ежедневное обновление", "#Контроль остатков денежных средств", "#Фильтрация по счетам в банках и статьям в кассе	"], },
				{ title: "Фильтры", info: ["По компаниям", "По банковским счетам", "По статьям движения денежных средств"] }
			]
		}
	},
}
</script>

<style lang="sass">
.bank-and-cash-container
	display: flex
	flex-direction: row
	min-height: 50%
	justify-content: space-between
	align-items: flex-start

	.main-info
		display: flex
		flex-direction: row
		flex-wrap: wrap
		.block-text
			display: flex
			flex-direction: column
			justify-content: space-between
			width: 354px
			height: 176.867px
			border-radius: 15px
			background: #FFF
			box-shadow: 3px 3px 20px 0px rgba(0, 0, 0, 0.10)
			margin-right: 19px
			padding-left: 10px
			.text
				color: #6E6E73
				font-family: Roboto,sans-serif
				font-size: 29px
				font-style: normal
				font-weight: 700
				text-align: left
				text-indent: 0
				padding-top: 10px
	.featchers-info
		display: flex
		flex-direction: row
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
			.text
				color: #6E6E73
				font-family: Roboto,sans-serif
				font-size: 29px
				font-style: normal
				font-weight: 700
				text-align: left
				text-indent: 0
</style>