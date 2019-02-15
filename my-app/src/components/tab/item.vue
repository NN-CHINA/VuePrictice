<template>
	<div class="itemWarp" @click="changePage">
		<span v-show='!selected'>
			<slot name='normalImg'></slot>
		</span>
		<span v-show='selected'>
			<slot name='selectedImg'></slot>
		</span>
		<span v-text='title' class="title" v-bind:style="{'color': selectedTextColor}"></span>
		</div>
</template>

<script type="text/javascript">
	export default{
		name:"Item",
		data:function() {
			return {
				selectedTextColor:'#bfbfbf',
			}
		},
		props: {
			title: {
				type: String,
			},
			page: {
				type: String,
			},
			sel: {
				type: String,
			},
			pagePath: {
				type: String,
			},
		},
		computed: {
			selected: function() {
				this.changeTextColor();
				if (this.sel == this.page) {
					return true;
				} else {
					return false;
				}
			}
		},
		methods: {
			changePage:function() {
				this.$router.push('/' + this.page);
				this.$emit('change', this.page);
				this.changeTextColor();
			},
			changeTextColor:function() {
				if (this.sel == this.page) {
					this.selectedTextColor = '#333';
				} else {
					this.selectedTextColor = '#bfbfbf';
				}
			}
		},

	}
</script>

<style>
	.itemWarp {
		display:flex;
		flex-direction:column;
		justify-content:space-around;
		align-items:center;
		font-size:12px;
	}
	.title {

	}
</style>