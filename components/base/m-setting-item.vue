<template>
	<view class="setting-item mf-horizontal-space-between" hover-class="hoverClass" @tap="onItemClick">
		<view class="mf-vertical-center" :class="iconClass">
			{{itemName}}
		</view>
		<view v-show="isShowRightArrow" class="icon iconfont icon-jinru mf-vertical-center"></view>
	</view>
</template>

<script>
	export default {
		props: {
			itemName: String,
			itemIndex: Number,
			iconClass: String,
			isShowRightArrow: {
				type: Boolean,
				default: false
			},

		},
		data() {
			return {

			}
		},
		methods: {
			onItemClick: function() {
				// console.log("组件内部单击测试:"+this.itemIndex);
				this.$emit("onItemClick", this.itemIndex)
			}
		}
	}
</script>

<style lang="scss" scoped>
	.setting-item {
		flex: 1;
		width: 100%;
		&.hoverClass {
			background-color: #f1f1f1;
		}

		padding: 24upx 0;
		border-bottom: solid 1upx #F1F1F1;

		view:first-child {
			color: #343434;
			font-size: 28upx;
			margin-left: 24upx;
			&:before {
				font-size: 40upx;
				color: #57BBFF;
				margin-right: 8upx;
			}
		}

		view:last-child {
			color: #C6C6C6;
			margin-right: 24upx;
		}
	}
</style>
