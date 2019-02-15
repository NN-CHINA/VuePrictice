<template>
	<div class="tabbarWarp">
		<div class="warp">
			<Item v-for='item in tabbarItems' :key='item.title' v-bind:title='item.title' v-on:change='selectedItem' v-bind:page='item.page' v-bind:sel='selected' :pagePath='item.pagePath'>
				<img v-bind:src='item.normalImg' slot='normalImg'>
				<img v-bind:src='item.selectedImg' slot='selectedImg'>
			</Item>
		</div>
	</div>
</template>

<script type="text/javascript">
	import Item from './item.vue'
	export default {
		name:"TabBar",
		components: {
			Item,
		},
		data:function() {
			return {
				selected:'home',
				tabbarItems:[
					{
						title:'首页',
						page:'home',
						normalImg:require('../../assets/tab_homePage_nor.png'),
						selectedImg:require('../../assets/tab_homePage_sel.png'),
						pagePath:'../../page/home/home',
					},
					{
						title:'我的',
						page:'mine',
						normalImg:require('../../assets/tab_mine_nor.png'),
						selectedImg:require('../../assets/tab_mine_sel.png'),
					},
				]
			}
		},
		methods: {
			selectedItem:function(res) {
				this.selected = res;
				console.log(res);
			}
		},
	}
</script>

<style>
	.tabbarWarp {
		position:fixed;
		bottom:0;
		left:0;
		width:100%;
		height:50px;
		background:#fff;
	}
	.warp {
		display:flex;
		flex-direction:row;
		justify-content:space-around;
		align-items:center;
	}
	.warp img {
		width:20px;
		height:20px;
		margin-top:10px;
	}
</style>