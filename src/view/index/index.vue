<template>
	<div class="content">
		<div class="content-bar">
			<van-notice-bar
				left-icon="volume-o"
				:text="notice"
			/>
		</div>

		<div class="content-title">{{ title }}</div>
		<van-grid class="content-grid" :column-num="2" :gutter="10">
			<van-grid-item v-for="(item, index) in apps" :key="index" @click="navTo(item)">
<!--				<i :class="item.icon" class="van-icon van-icon-photo-o van-grid-item__icon"></i>-->
				<van-image
					width="100"
					height="100"
					:src="item.image"
				/>
				<span class="van-grid-item__text content-grid-text">{{ item.title }}</span>
			</van-grid-item>
		</van-grid>
	</div>
</template>

<script>
import {Row, Col, Icon, Cell, CellGroup, Grid, GridItem, NoticeBar, Image} from 'vant';

export default {
  components: {
    [Grid.name]: Grid,
    [GridItem.name]: GridItem,
    [Row.name]: Row,
    [Col.name]: Col,
    [Icon.name]: Icon,
    [Cell.name]: Cell,
    [CellGroup.name]: CellGroup,
    [NoticeBar.name]: NoticeBar,
    [Image.name]: Image
  },
	data() {
		return {
			title: process.env.TITLE || 'Ai产品',
			notice: process.env.NOTICE || '在代码阅读过程中人们说脏话的频率是衡量代码质量的唯一标准。',
			apps: process.env.APPS || [
				{
					title: 'ChatGPT',
					url: 'https://chat-next-web-nu-one.vercel.app/',
					image: '/static/img/img1.jpeg'
				},
				{
					title: 'BingAi',
					url: 'https://go-proxy-bingai-iota-six.vercel.app/',
					image: '/static/img/img2.png'
				},
				{
					title: 'ChatGPT Midjourney',
					url: 'https://chatgpt-with-midjourney-ecru.vercel.app/',
					image: '/static/img/img3.png'
				},
				{
					title: 'ChatGPT Academic',
					url: 'http://20.222.146.186:8080/',
					image: '/static/img/img4.png'
				}
			]
		};
	},
	methods: {
		navTo(item) {
			window.open(item.url, '_blank');
		}
	}
};
</script>

<style lang="less">
.content {
	display: flex;
	//height: calc(100vh - 200px);
	flex-direction: column;
	justify-content: center;
	align-items: center;

	&-bar {
		margin-top: 20px;
		width: 100%;
	}

	&-title {
		font-size: 20px;
		font-weight: bold;
		margin-top: 20px;
		background: white;
		width: calc(100% - 30px);
		text-align: center;
		padding: 10px;
	}
	&-grid {
		margin-top: 20px;
		width: 100%;
		&-text {
			font-size: 19px;
			margin-top: 10px;
		}
		&-image {
			width: 100px;
			height: 100px;
		}
	}
}
</style>
