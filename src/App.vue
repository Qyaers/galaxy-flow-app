<template>
	<headerComponent></headerComponent>
	<mainComponent></mainComponent>
	<footerComponent></footerComponent>
</template>

<script>
import headerComponent from './components/Header.vue'
import mainComponent from './components/Main.vue'
import footerComponent from './components/Footer.vue'
export default {
	components: {
		headerComponent, mainComponent, footerComponent
	},
	data() {
		return {

		}
	},
}
</script>

<style lang="css"></style>
