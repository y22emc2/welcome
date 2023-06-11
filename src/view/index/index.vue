<template>
	<div class="content">
		<div class="content-title">Ai产品</div>
		<van-grid class="content-grid" :column-num="2" :gutter="10">
			<van-grid-item v-for="(item, index) in apps" :key="index" @click="navTo(item)">
				<i :class="item.icon" class="van-icon van-icon-photo-o van-grid-item__icon"></i>
				<span class="van-grid-item__text content-grid-text">{{ item.title }}</span>
			</van-grid-item>
		</van-grid>
	</div>
</template>

<script>
import {Row, Col, Icon, Cell, CellGroup, Grid, GridItem} from 'vant';

export default {
  components: {
    [Grid.name]: Grid,
    [GridItem.name]: GridItem,
    [Row.name]: Row,
    [Col.name]: Col,
    [Icon.name]: Icon,
    [Cell.name]: Cell,
    [CellGroup.name]: CellGroup
  },
	data() {
		return {
			apps: [
				{
					title: 'ChatGPT',
					url: 'https://chat-next-web-nu-one.vercel.app/',
					image: ''
				},
				{
					title: 'BingAi',
					url: 'https://go-proxy-bingai-iota-six.vercel.app/',
					image: ''
				},
				{
					title: 'ChatGPT-Midjourney',
					url: 'https://chatgpt-with-midjourney-ecru.vercel.app/',
					image: ''
				},
				{
					title: 'ChatPDF',
					url: 'http://20.222.146.186:8080/',
					image: ''
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
			font-size: 20px;
			margin-top: 10px;
		}
		&-image {
			width: 100px;
			height: 100px;
		}
	}
}
</style>
