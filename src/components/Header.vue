<template>
	<div class="header">
		<header class="header-menu">
			<img class="header-menu__icon" src="../assets/logo.png" alt="logo">
			<nav class="nav">
				<li class="nav__item" v-for="(item, index) in  links " :key="index">
					<a class="nav__link" :href="item">{{ index }}</a>
				</li>
			</nav>

		</header>
		<div class="sub-header">
			<h1 class="sub-header__title">Galaxy Flow</h1>
		</div>
	</div>
</template>

<script>
export default {
	data() {
		return {
			links: {
				"О компании": "#about",
				"Наш продукт": "#product",
				"Как это работает?": "#about-product",
				"FAQ": "#faq",
				"Тарифы": "#tariffs",
			}
		}
	}
}

</script>
<style lang="sass">
.header-menu
	display: flex
	flex-direction: row
	height: 20%
	width: 100vw
	background: rgba(245, 245, 247, 0.75)
	flex-shrink: 0
	align-items: center
	position: sticky
	top: 0
	transition: 1s
	.header-menu__icon
		max-width: 10%
		max-height: 100%
		min-height: 20%
		flex-shrink: 0
	.nav
		width: 100%
		display: flex
		flex-direction: row
		align-items: center
		padding-left: 10%
		@media screen and (max-width: 1000px)
			padding-left: 20px
		@media screen and (max-width: 800px)
			padding: 5px
			margin: 0 auto
		&__item
			list-style-type: none
			&__item>.nav__link 
				text-decoration: none
				color: white
			&:last-child
				padding-right: 2vw
	.nav__item ~ .nav__item
		padding-left: 6vw
		@media screen and (max-width: 800px)
			padding-left: 20px
			margin: 0 auto
.sub-header 
	height: 100vh
	min-width: 100vw
	background: url('../assets/subHeaderBG.png')
	background-size: cover
	background-repeat: no-repeat
	@media screen and (max-width: 800px)
		display: flex
		justify-content: center
		align-items: center
		height: 80vh
		padding-bottom: 20%
.sub-header__title
	padding-left: 20%
	padding-top: 10%
	text-align: center
	font-size: 9.375em
	background: linear-gradient(74deg, rgba(205, 76, 250, 0.58) 38.7%, rgba(123, 70, 166, 0.60) 80.75%)
	background-clip: text
	-webkit-background-clip: text
	-webkit-text-fill-color: transparent
	@media screen and (max-width: 1200px)
		padding-left: 30%
		padding-top: 10%
		font-size: 7em
	@media screen and (max-width: 800px)
		font-size: 15em
		padding: 10%
		background: linear-gradient(100deg, rgba(205, 50, 240, 0.85) 38.7%, rgba(123, 70, 166, 0.40) 80.75%)
		background-clip: text
	@media screen and (max-width: 600px)
		padding: 0
		padding-top: 50%
		font-size: 10em
		background: linear-gradient(100deg, rgba(200, 50, 240, 1) 100%, rgba(123, 70, 166, 0.40) 80.75%)
		background-clip: text
</style>