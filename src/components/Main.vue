<template>
	<main class="main">
		<aboutComponent></aboutComponent>
		<productComponent></productComponent>
		<howItWorksComponent></howItWorksComponent>
		<tariffsComponent></tariffsComponent>
	</main>
</template>

<script>
import aboutComponent from './AboutComponent.vue';
import productComponent from './ProductComponent.vue';
import howItWorksComponent from './HotItWorksComponent.vue';
import tariffsComponent from './TariffsComponent.vue';
import footerComponent from './Footer.vue'

export default {
	components: {
		aboutComponent,productComponent,howItWorksComponent, tariffsComponent,footerComponent
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
