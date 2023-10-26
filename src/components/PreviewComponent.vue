<template>
	<div class="preview">
		<div class="preview__container container">
			<div class="title">
				<h1>galaxy data</h1>
			</div>
			<div class="preview-info">
				<div class="text__info">
					<h2 class="text__info-titile">Добро пожаловть!</h2>
					<p class="text__info-description">Мы Galaxy data, представляем вам наш стартап, благодаря которому вы
						сможете решить все ваши проблемы с
						отчётностью и не только, более подробнее о нас вы можете прочитать в разделе "О нас" и "Как мы работаем"
					</p>
				</div>
				<div class="preview-info__log">
					<img src="" alt="123">
				</div>
			</div>
		</div>
	</div>
</template>
<script>
export default {

}
</script>
<style lang="css">
.preview {

	width: 100%;
	height: 750px;
	flex-shrink: 0;
	background: url("../assets/123.webp");
	background-size: cover;
	background-repeat: no-repeat;
}

.preview__container {
	display: flex;
	flex-direction: column;
}

.preview-info {
	margin-top: 60px;
	display: flex;
	flex-direction: row-reverse;
	align-items: center;
	justify-content: space-around;

}

.text__info {
	display: flex;
	flex-direction: column;
	align-items: center;
	width: 500px;

}

.title {
	display: flex;
	height: 148px;
	flex-direction: column;
	justify-content: center;
	flex-shrink: 0;
	color: #FFF;
	text-transform: uppercase;
	text-align: center;
	text-shadow: 0px 4px 4px rgba(255, 255, 255, 0.39);
	font-family: Inter;
	font-size: 60px;
	font-style: normal;
	font-weight: 400;
	line-height: normal;
}
</style>