<template>
	<div id="product" class="product container">
		<div class="product__title">
			<h2>Наш продукт</h2>
		</div>
		<div class="current-info-btns">
			<button v-for="tab in tabs" :class="['btn', { active: currentTab === tab.component }]"
				@click="changeComponent(tab.component)" :disabled="tab.disabledBtn">
				{{ tab.text }}
			</button>
		</div>
		<transition name="bounce">
			<component :is="currentTab"> </component>
		</transition>
		<div class="product__report">
			<h3>Пример финансового отчёта Fin Flow</h3>
			<iframe class="report-view" title="Report Section"
				src="https://app.fabric.microsoft.com/view?r=eyJrIjoiYTdhMmQ1N2YtMTE4OC00NzFlLWI0ZDEtMjIyM2U1OTVmMWQ1IiwidCI6ImI4MmQ2N2FmLWJmMGQtNGJjOS04Y2QxLWE0ZWQwZTBlMzVjOSIsImMiOjl9&pageName=ReportSectioneb70caf7e92ea1477416"
				frameborder="0" allowFullScreen="true"></iframe>
		</div>
	</div>
</template>
<script>
import ofrComponent from '../components/OFR.vue';
import oddcComponent from '../components/ODDC.vue';
import bankAndCashComponent from '../components/BankAndCash.vue';
import creditsAndLoansComponent from '../components/CreditsAndLoans.vue';
export default {
	components: {
		ofrComponent,
		oddcComponent,
		bankAndCashComponent,
		creditsAndLoansComponent
	},
	data() {
		return {
			currentTab: "ofrComponent",
			tabs: [
				{ text: "ОФР", component: "ofrComponent", disabledBtn: true },
				{ text: "ОДДС", component: "oddcComponent", disabledBtn: false },
				{ text: "Банк и касса", component: "bankAndCashComponent", disabledBtn: false },
				{ text: "Кредиты и займы", component: "creditsAndLoansComponent", disabledBtn: false },
			],
			disabledBtn: true
		}
	},
	methods: {
		changeComponent(component) {
			for (const key in this.tabs) {
				if (this.tabs[key].component == component) {
					this.currentTab = component
					this.tabs[key].disabledBtn = !this.tabs[key].disabledBtn
				} else {
					if (this.tabs[key].disabledBtn) {
						this.tabs[key].disabledBtn = !this.tabs[key].disabledBtn
					}
				}
			}
		},
	},
}
</script>
<style lang="sass">

.current-info-btns
	display: flex
	flex-direction: row
	justify-content: center
	margin-bottom: 5vh
	.btn
		margin-left: 3vw
		min-height: 15%
		max-width: 22.5%
.product__report
	display: flex
	flex-direction: column
	justify-content: center
	width: 100%
	height: 100%
	margin-top: 3%
	h3
		position: relative
		color: #ABBED7
	.report-view
		min-width: 80%
		min-height: 60vh
		box-shadow: 3px 3px 20px 0px rgba(0, 0, 0, 0.10)
		border-radius: 20px
.bounce-enter-active 
	animation: bounce-in 1.5s

@keyframes bounce-in
	0%
		transform: scale(0)
	100% 
		transform: scale(1)
</style>