<template>
	<main class="main">
		<preview></preview>
		<about></about>
		<product></product>
		<howItWorks></howItWorks>
		<tariff></tariff>
	</main>
</template>

<script>
import preview from './PreviewComponent.vue'
import about from './AboutComponent.vue';
import product from './ProductComponent.vue';
import howItWorks from './HotItWorksComponent.vue';
import tariff from './TariffsComponent.vue';

export default {
	components: {
		preview, about, howItWorks, product, tariff
	},
	data() {
		return {

		}
	}
}

</script>


<style lang="css">
.main {
	flex: 1 1 auto;
}
</style>
