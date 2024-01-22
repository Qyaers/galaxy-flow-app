<template>
	<div class="requirements container">
		<div class="requirements__item">
			<div class="item__container" v-for="item in requirements">
				<div class="text__title">
					<h3>
						{{ item.title }}
					</h3>
				</div>
				<div class="text__block">
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
	props: {
		requirements: Array
	}
}
</script>
<style lang="sass">
.requirements
	display: flex
	flex-direction: row
	min-width: 100%
	justify-content: space-between
	margin: 0
	margin-bottom: 5vh
	.requirements__item
		width: 100%
		display: flex
		flex-direction: row
		justify-content: space-evenly
		align-items: center
		@media screen and (max-width: 1100px)
			flex-wrap: wrap
		.text__block
			border-radius: 15px
			background: linear-gradient(100deg, rgba(255, 255, 255, 0.10) 0%, rgba(171, 190, 215, 0.10) 100%)
			box-shadow: 3px 3px 20px 0px rgba(0, 0, 0, 0.10)
			display: flex
			flex-direction: column
			justify-content: space-between
			width: 350px
			height: 174px
			border-radius: 15px
			box-shadow: 3px 3px 20px 0px rgba(0, 0, 0, 0.10)
			padding: 10px
			margin-bottom: 20px
			@media screen and (max-width: 1800px) 
				width: 320px
				height: 174px
			@media screen and (max-width: 1300px) 
				width: 300px
				height: 174px
			@media screen and (max-width: 1100px)
				justify-content: space-evenly
			.text
				font-size: 1.6em
				text-align: left
				@media screen and (max-width: 1300px)
					font-size: 1.2em
				@media screen and (max-width: 1100px)
					text-align: center
	.item__container
		@media screen and (max-width: 1200px)
			width: 300px
		@media screen and (max-width: 1000px)
	.text__title
		text-align: center
		width: 350px
		@media screen and (max-width: 1000px)
			width: 100%
	
	h3
		font-size: 1.36em
		@media screen and (max-width: 1200px)
			font-size: 1.2em
		@media screen and (max-width: 1000px)
			font-size: 1.5em
			text-align: center
</style>