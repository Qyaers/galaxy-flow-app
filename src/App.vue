<template>
	<headerComponent></headerComponent>
	<aboutComponent></aboutComponent>
	<productComponent></productComponent>
	<aboutProductComponent></aboutProductComponent>
	<faqComponent></faqComponent>
	<tariffsComponent></tariffsComponent>
	<footerComponent></footerComponent>
</template>

<script>
import headerComponent from './components/Header.vue'
import aboutComponent from './components/About.vue';
import productComponent from './components/ProductComponent.vue';
import aboutProductComponent from './components/AboutProduct.vue';
import faqComponent from './components/FAQ.vue';
import tariffsComponent from './components/TariffsComponent.vue';
import footerComponent from './components/Footer.vue'

export default {
	components: {
		headerComponent,
		aboutComponent,
		productComponent,
		aboutProductComponent,
		faqComponent,
		tariffsComponent,
		footerComponent
	},
	data() {
		return {

		}
	},
}
</script>

<style lang="css"></style>
