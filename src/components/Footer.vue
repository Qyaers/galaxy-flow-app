<template>
	<footer class="footer">
		<div class="footer__info">
			<p>ООО “Элемент-Глобал”</p>
			<p>ИНН: 1800007293</p>
			<p>© 2023 Galaxy Flow. Все права защищены</p>
		</div>
		<div class="footer__social-media">
			<p>Связаться с нами:</p>
			<div class="social-media-items" v-for="(item, index) in image" :key="index">
				<a href:prevent>
					<img class="social-media-icons" :src="item" alt="socialmediaimage {{ index }}">
				</a>
			</div>
		</div>
	</footer>
</template>


<script>
export default {
	data() {
		return {
			image: ["src/assets/Telgram.png", "src/assets/Viber.png", "src/assets/Whatsapp.png"]
		}
	}
}
</script>
<style lang="sass">
.footer 
	display: flex
	justify-content: space-around
	flex-direction: row
	min-height: 10vh
	width: 100vw
	background: #6F7073
	p
		color: white
		font-size: 18px
		line-height: 30px
	&__social-media
		display: flex
		flex-direction: row
		align-items: center
.social-media-icons
	padding-left: 0.5vw
.footer__info
	p
		&:last-child
			margin-top: 20px
			padding-bottom: 10px
</style>