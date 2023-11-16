<template>
	<div class="product container">
		<div class="product__title">
			<h2>Наш продукт</h2>
		</div>
		<div class="current-info-btns">
			<button v-for=" tab  in  tabs " :key="tab" :class="['btn', { active: currentTab === tab }]"
				@click="currentTab = tab" :disabled="disableActiveButton">
				{{ tab }}
			</button>
			<keep-alive>
				<component :is="currentTabComponent"> </component>
			</keep-alive>
		</div>
		<component :is="currentTabComponent">
		</component>
		<iframe class="product__view" title="Fin_Flow_Site" width="860" height="780"
			src="https://app.powerbi.com/view?r=eyJrIjoiZjM2ODc0ZWUtOWVmYy00YTQyLTk4M2EtZWJlYzE4ZDE0ZDBlIiwidCI6ImI4MmQ2N2FmLWJmMGQtNGJjOS04Y2QxLWE0ZWQwZTBlMzVjOSIsImMiOjl9&pageName=ReportSectioneb70caf7e92ea1477416"
			frameborder="0" allowFullScreen="true"></iframe>
	</div>
</template>
<script>
// import ofrComponent from '../components/OFR.vue'
// import oddcComponent from '../components/ODDC.vue'
// import bankAndCashComponent from '../components/BankAndCash.vue'
export default {
	components: {
		// ofrComponent,
		// oddcComponent,
		// bankAndCashComponent
	},
	data() {
		return {
			currentTab: "Header",
			tabs: ["Header", "ОДДС", "Банк и касса"]
		}
	},
	computed: {
		currentTabComponent() {
			console.log(this.currentTab);
			this.dissabled == true
			return 'tab-' + this.currentTab.toLowerCase()
		}
	}
}
</script>
<style lang="sass">
.product__view
	margin: 0 auto
	margin-top: 100px
</style>