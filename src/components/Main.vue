<template>
	<main class="main">
		<aboutComponent></aboutComponent>
		<productComponent></productComponent>
		<aboutProductComponent></aboutProductComponent>
		<tariffsComponent></tariffsComponent>
	</main>
</template>

<script>
import aboutComponent from './About.vue';
import productComponent from './ProductComponent.vue';
import aboutProductComponent from './AboutProduct.vue';
import tariffsComponent from './TariffsComponent.vue';
import footerComponent from './Footer.vue'

export default {
	components: {
		aboutComponent, productComponent, aboutProductComponent, tariffsComponent, footerComponent
	},
	data() {
		return {

		}
	}
}

</script>


<style lang="sass">
.main 
	flex: 1 1 auto

</style>
