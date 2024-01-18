<template>
	<div class="product__item" :class="item.class">
		<div class="item__image">
			<img :src="item.img" alt="">
		</div>
		<div class="item__text">
			<h3 class="title">{{ item.title }}</h3>
			<p class="text">{{ item.text }}</p>
		</div>
	</div>
</template>
<script>
export default {
	props: {
		item: Object
	}
}
</script>
<style lang="sass">
.product__item
	display: flex
	width: 100%
	padding-bottom: 50px
.item__image
	width: 60%
	padding-right: 50px
	@media screen and (max-width: 1000px)
		padding-right: 20px
.item-direction
	flex-direction: row
	&-reverse
		flex-direction: row-reverse
.item__text
	display: flex
	flex-direction: column
	justify-content: center
	align-items: center
	padding-right: 50px
	@media screen and (max-width: 1000px)
		padding-right: 10px
	.title
		padding-bottom: 20px
	h3
		color: #6E6E73
		text-shadow: rgba(171,190,215) 0px -5px 20px
		font-size: 2em
		@media screen and (max-width: 1000px)
			font-size: 1.75em
	p
		font-size: 1.8em
		@media screen and (max-width: 1000px)
			font-size: 1.45em
	h3,p
		text-align: center
</style>