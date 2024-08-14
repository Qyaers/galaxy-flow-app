<template>
	<div id="about-product" class="about-product">
		<div class="running-line ticker-wrapper">
			<div class="ticker-wrapper__first-half">
				<p>#контролируй бизнес</p>
				<p>#управляй эффективно</p>
				<p>#анализируй данные</p>
			</div>
			<div class="ticker-wrapper__second-half">
				<p>#находи аномалии</p>
				<p>#прогнозируй финансы</p>
				<p>#отслеживай показатели</p>
			</div>
		</div>
		<div class="info">
			<div class="info__container container">
				<h2>Как это работает?</h2>
				<div class="timeline">
					<div class="timeline__component">
						<div class="timeline__date timeline__date--right">
						</div>
					</div>
					<div class="timeline__middle">
						<div class="timeline__point"></div>
					</div>
					<div class="timeline__component timeline__component--bg">
						<h3 class="timeline__title">#001</h3>
						<span class="timeline__paragraph">Настраиваются отчёты в 1С</span>
					</div>
					<div class="timeline__component timeline__component--bg">
						<h3 class="timeline__title">#002</h3>
						<span class="timeline__paragraph">Выгружаются исходные данные из 1С</span>
					</div>
					<div class="timeline__middle">
						<div class="timeline__point"></div>
					</div>
					<div class="timeline__component">
						<div class="timeline__date timeline__date">
						</div>
					</div>
					<div class="timeline__component">
						<div class="timeline__date timeline__date--right">
						</div>
					</div>
					<div class="timeline__middle">
						<div class="timeline__point"></div>
					</div>
					<div class="timeline__component timeline__component--bg">
						<h3 class="timeline__title">#003</h3>
						<span class="timeline__paragraph">Исходные данные загружаются на сервер</span>
					</div>
					<div class="timeline__component timeline__component--bg">
						<h3 class="timeline__title">#004</h3>
						<span class="timeline__paragraph">Данные обрабатываются на сервере</span>
					</div>
					<div class="timeline__middle">
						<div class="timeline__point"></div>
					</div>
					<div class="timeline__component">
						<div class="timeline__date timeline__date">
						</div>
					</div>
					<div class="timeline__component">
						<div class="timeline__date timeline__date--right">
						</div>
					</div>
					<div class="timeline__middle">
						<div class="timeline__point"></div>
					</div>
					<div class="timeline__component timeline__component--bg">
						<h3 class="timeline__title">#005</h3>
						<span class="timeline__paragraph">Формируется интерактивный отчёт</span>
					</div>
					<div class="timeline__component timeline__component--bg">
						<h3 class="timeline__title">#006</h3>
						<span class="timeline__paragraph">Отчёт предоставляется клиенту</span>
					</div>
					<div class="timeline__middle">
						<div class="timeline__point"></div>
					</div>
					<div class="timeline__component">
						<div class="timeline__date timeline__date">
						</div>
					</div>
					<div class="timeline__component">
						<div class="timeline__date timeline__date--right">
						</div>
					</div>
					<div class="timeline__middle">
					</div>
					<div class="timeline__component">
						<div class="timeline__date timeline__date--right">
						</div>
					</div>
				</div>
				<div class="timeline__component--bg timeline__ending">
					<div class="timeline__paragraph"><span class="">Интерактивный отчёт Power BI </span><img
							src="../assets/PowerBI.png" alt=""></div>
				</div>
			</div>
		</div>
	</div>
</template>
<script>
export default {


}
</script>
<style lang="sass">
.about-product
	margin-top: 50px
	span
		display: table-cell
		vertical-align: middle
		text-align: center
		width: 10%
		height: 20%
		color: #FFF
		text-align: center
		font-size: 1.5em
		line-height: normal
	h3
		color: #FFF
		font-size: 1.8em
	.running-line 
		height: 5vh
		width: 100%
		position: relative
		overflow: hidden
		div.ticker-wrapper__first-half,.ticker-wrapper__second-half 
			display: flex
			flex-direction: row
			align-items: center
			overflow: hidden
			width: 100%
			height: 43px
			transform: translate(100%, 0)
			p 
				color: #6E6E73
				font-size: 2em
				text-transform: uppercase
				@media screen and (max-width: 1320px)
					font-size: 1.6em
					padding-bottom: 20px

				@media screen and (max-width: 1100px)
					font-size: 1.2em
					padding-bottom: 20px

				@media screen and (max-width: 800px)
					font-size: 1em
					padding-bottom: 20px
		$duration: 30s
		.ticker-wrapper__first-half, .ticker-wrapper__second-half 
			display: flex
			flex-direction: row
			justify-content: space-around
			align-items: center
			position: absolute
			top: 0
			right: 0
			animation: ticker $duration infinite linear forwards
		.ticker-wrapper__second-half
			animation: $duration ticker $duration/2 infinite linear forwards
		@keyframes ticker 
			0% 
				transform: translate(100%, 0)
			50% 
				transform: translate(0, 0)
			100% 
				transform: translate(-100%, 0)
	.info
		background: #ABBED7
		max-height: 80vh
		overflow-x: scroll
	.info::-webkit-scrollbar
			width: 0
	.info__container

// timeLine
.timeline
	max-width: 100%
	margin: 0px auto
	display: grid
	grid-template-columns: 1fr 0.2% 1fr
	
.timeline__component
	margin: 0 2% 3% 2%
.timeline__component--bg
	padding: 1.5em
	border-radius: 30px
	border: 2px solid #000
	background: #6F7073
	box-shadow: 5px 5px 10px 0px rgba(0, 0, 0, 0.45)
.timeline__date--right
	text-align: right
.timeline__middle
	position: relative
	background: white
.timeline__point
	position: absolute
	width: 24px
	height: 24px
	top: 0
	transform: translateX(-45%)
	border-radius: 5px
	border: 1px solid #000
	background: #ABBED7
	box-shadow: 0px 4px 4px 0px rgba(0, 0, 0, 0.25)
.timeline__title,.timeline__paragraph
	text-transform: uppercase
	text-align: center
.timeline__ending
	display: flex
	flex-direction: column
	align-items: center
	justify-content: space-around
	margin: 0 auto
	width: 389px
	height: 168.995px
	flex-shrink: 0
	margin-bottom: 50px
</style>