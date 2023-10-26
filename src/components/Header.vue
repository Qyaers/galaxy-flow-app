<template>
	<header class="header">
		<nav class="nav container">
			<li class="nav__item" v-for="(item, index) in  links " :key="index">
				<a class="nav__link" :href="item">{{ index }}</a>
			</li>
		</nav>
	</header>
</template>

<script>
export default {
	data() {
		return {
			links: {
				"О нас": "#about",
				"Продукт": "#about",
				"Как мы работаем": "#about",
				"Контакты": "#about",
				"Тарифы": "#about"
			}
		}
	}
}

</script>
<style lang="css">
.header {
	display: flex;
	height: 100px;
	width: 100%;
	background: rgba(0, 0, 0, 0.78);
	flex-shrink: 0;
	position: sticky;
	top: 0px;
}

.nav {
	display: flex;
	flex-direction: row;
	align-items: center;
	justify-content: space-around;
}

.nav__item {
	list-style-type: none;
}

.nav__item>.nav__link {
	text-decoration: none;
	color: white;
}

.a:hover {
	color: rgba(0, 0, 0, 0.089);
}
</style>