<template>
	<view class="tab">
		<scroll-view class="tab-scoll" scroll-x>
			<view class="tab-scoll_box">
				<view class="tab-scoll_item" v-for="(item,index) in list" :key="index">
					{{item.name}}
				</view>
			</view>
		</scroll-view>
		<view class="tab-gear">
			<text class="iconfont icon-apps"></text>
		</view>
	</view>
</template>

<script>
	export default {
		props:{
			list:{
				type:Array,
				default(){
					return []
				}
			}
		},
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
	@import "../../common/css/icons.css" ;
	.tab{
		height: 45px;
		display: flex;
		align-items: center;
		background-color: #fff;
		border-bottom: 1px solid #ccc;
		box-sizing: border-box;
		width: 100vw;
		
		.tab-scoll{
			flex: 7;
			overflow: hidden;
			box-sizing: border-box;
			
			.tab-scoll_box{
				display: flex;
				height:45px;
				align-items: center;
				flex-wrap: nowrap;
				// overflow:hidden;
				// box-sizing: border-box;
				
				.tab-scoll_item{
				flex-shrink: 0;	
				padding: 0 10px;
				// box-sizing: border-box;
				}
			}
		}
		.tab-gear{
			flex: 1;
			// width: 45px;
			height: 45px;
			display: flex;
			align-items: center;
			justify-content: center;
			position: relative;
			&::after{
				content: '';
				position: absolute;
				top: 12px;
				bottom: 12px;
				left: 0;
				width: 1px;
				background-color: #ddd;
			}
		}
	}

</style>
