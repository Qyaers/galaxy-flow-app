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
				"Как мы работаем": "#about-product",
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
	height: 9.48vh
	width: 100vw
	background: rgba(245, 245, 247, 0.75)
	flex-shrink: 0
	align-items: center
	position: sticky
	top: 0vh
	transition: 1s
	.header-menu__icon
		max-width: 10%
		height: 100%
		flex-shrink: 0
	.nav
		width: 100%
		display: flex
		flex-direction: row
		align-items: center
		padding-left: 10vw

		&__item
			list-style-type: none
			&__item>.nav__link 
				text-decoration: none
				color: white
			&:last-child
				padding-right: 2vw
	.nav__item ~ .nav__item
		padding-left: 6vw
.sub-header 
	min-height: 100vh
	min-width: 100vw
	background: url('../assets/subHeaderBG.png')
	background-size: cover
	background-repeat: no-repeat
.sub-header__title
	padding-left: 14vw
	padding-top: 10vw
	text-align: center
	font-size: 9.375em
	background: linear-gradient(74deg, rgba(205, 76, 250, 0.58) 38.7%, rgba(123, 70, 166, 0.60) 80.75%)
	background-clip: text
	-webkit-background-clip: text
	-webkit-text-fill-color: transparent
	@media screen and (max-width: 1800px)
		padding-left: 40vw
		padding-top: 15vw
		font-size: 7em
	@media screen and (max-width: 1330px) 
		display: none
</style>