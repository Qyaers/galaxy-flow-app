<template>
	<headerComponent></headerComponent>
	<mainComponent></mainComponent>
	<footerComponent></footerComponent>
</template>

<script>
import headerComponent from './components/Header.vue'
import footerComponent from './components/Footer.vue'
import mainComponent from './components/Main.vue'
export default {
	components: {
		mainComponent, headerComponent, footerComponent
	},
	data() {
		return {

		}
	}
}
</script>

<style lang="css"></style>
