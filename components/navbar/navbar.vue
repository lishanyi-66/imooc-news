<template>
		<view class="navbar">
			<view class="navbar-fixed">
				<!-- 状态栏 -->
				<view class="" :style="{height: statusBarHeight+'px'}">
					
				</view>
				<view class="navbar-content" :style="{height:navHeight+'px', width:windowWidth+'px'}">
					<view class="navbar-search" style="{height: menuButtonInfo.height+'px'}">
						<view class="navbar-search-icon">
							<text class="iconfont icon-search"></text>
						</view>
						<view class="navbar-search-title">
							uni-app
						</view>
					</view>
				</view>
			</view>
			<view class="" :style="{height:navHeight+statusBarHeight+'px' }">
				
			</view>
		</view>
</template>

<script>
	export default {
		data() {
			return {
				statusBarHeight: 20,
				navHeight:44,
				// menuButtonInfo:0,
				windowWidth:375
			};
			
		},
		created(){
			// 获取系统信息
			const info = uni.getSystemInfoSync()
			// 设置状态栏高度
			this.statusBarHeight=info.statusBarHeight
			this.windowWidth=info.windowWidth
			console.log(info)
			
			// #ifndef H5 || APP-PLUS || MP-ALIPAY
			// 获取胶囊的位置
			const menuButtonInfo=uni.getMenuButtonBoundingClientRect()
			console.log(menuButtonInfo)
			// 获取导航栏的高度
			// (胶囊底部的高度-状态栏的高度)+(胶囊顶部的高度-状态栏的高度)=导航栏的高度
			let navBarHeight=(menuButtonInfo.bottom-info.statusBarHeight)+(menuButtonInfo.top-info.statusBarHeight)
			console.log(navBarHeight)
			// 导航的宽度
			this.windowWidth=menuButtonInfo.left
			// var sysinfo = uni.getSystemInfo(),
			//         statusHeight = sysinfo.statusBarHeight,
			//         isiOS = sysinfo.system.indexOf('iOS') > -1,
			//         navHeight;
			//     if (!isiOS) {
			//         navHeight = 48;
			//     } else {
			//         navHeight = 44;
			//     }
			//     this.statusHeight = statusHeight;
			//     this.navHeight = navHeight;
			// #endif
		}
		
	}
</script>
	
<style lang="scss">
	@import '../../common/css/icons.css';
	.navbar{
		// width: 100%;
		.navbar-fixed{
			width: 100%;
			position: fixed;
			top: 0;
			left: 0;
			z-index: 99;
			background-color: $mk-base-color;
			.navbar-content{
				display: flex;
				align-items: center;
				justify-content: center;
				// width: 100%;
				// height: 40px;
				padding: 0 15px;
				box-sizing: border-box;
				.navbar-search{
					display: flex;
					align-items: center;
					padding: 0 10px;
					width: 100%;
					height: 32px;
					border-radius: 30px;
					background-color: #fff;
					
					.navbar-search-icon{
						// width: 15px;
						// height: 15px;
						// background-color: $mk-base-color;
						font-size: 10px;
					}
					.navbar-search-title{
						margin-left: 5px;
						font-size: 14px;
						width: 100%;
					}
				}
			}
		}
	}
	
	
</style>
