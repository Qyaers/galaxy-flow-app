<template>
	<footer class="footer">
		<div class="footer-container container">
			<div class="footer__info">
				<p>ООО “Элемент-Глобал”</p>
				<p>ИНН: 1800007293</p>
				<p>Icons by <a href="https://icons8.com/">Icons8</a></p>
				<p>© 2023-{{ currentYear }} Galaxy Flow. Все права защищены</p>
			</div>
			<div class="footer__social-media">
				<p>Наши контакты</p>
				<div class="social-media__icons">
					<div class="icons-items" v-for="(item, index) in  image " :key="index">
						<a :href=item.link target="_blank">
							<img class="icons__item" :onclick="item.event" :src="item.icon" alt="socialmediaimage">
						</a>
					</div>
				</div>
				<div class="social-media__text">
					<p>element-global18@yandex.ru</p>
					<p>+7 922 520-19-00</p>
				</div>
			</div>
		</div>
	</footer>
</template>


<script>
export default {
	data() {
		return {
			image: [
				{
					icon: "img/telegram.png", link: "https://t.me/galaxyflowofficial", event: "ym(96037055,'reachGoal','telegram');"
				},
				{
					icon: "img/viber.png", link: "viber://chat?number=+79225201900", event: "ym(96037055,'reachGoal','viber');"
				},
				{
					icon: "img/whatsapp.png", link: "https://wa.me/79225201900", event: "ym(96037055,'reachGoal','whatsapp');"
				},
				{
					icon: "img/email.png", link: "mailto:element-global18@yandex.ru", event: "ym(96037055,'reachGoal','email');"
				}
			],
		}
	},
	methods: {
		isMobile() {
			if (/Android|webOS|iPhone|iPad|iPod|BlackBerry|BB|PlayBook|IEMobile|Windows Phone|Kindle|Silk|Opera Mini/i.test(navigator.userAgent)) {
				this.image[1].link = "viber://add?number=79225201900";
			} else {
				this.image[1].link = "viber://chat?number=+79225201900";
			}
		}
	},
	mounted() {
		this.isMobile();
	},
	computed: {
		currentYear() {
			return new Date().getFullYear();
		}
	}
}
</script>
<style lang="sass">
.footer 
	max-height: 10%
	width: 100%
	background: #6F7073
.footer-container
	display: flex
	justify-content: space-between
	flex-direction: row
	p
		color: white
		font-size: 1em
		line-height: 30px
		a
			color: white
			font-size: 1em
			line-height: 30px
			text-decoration: underline
	@media screen and (max-width: 800px)
		font-size: 0.85em
		justify-content: space-around
	.footer__social-media
		display: flex
		flex-direction: column
		align-items: center
	.social-media__icons
		display: flex
		flex-direction: row
		align-items: center
		justify-content: center
		.icons__item
			padding-left: 0.5vw
			max-width: 80px
			max-height: 80px
	.social-media__text
		p
			text-align: right
.footer__info
	display: flex
	flex-direction: column
	justify-content: space-between
	p
		&:last-child
			padding-bottom: 10px
			@media screen and (max-width: 800px)
				font-size: 0.85em
</style>