<template>
	<view class="navbar">
		<view class="navbar-fixed">
			<view class="navbar-content">
				<view class="navbar-search">
						<view class="navbar-search-icon">
							
						</view>
						<view class="navbar-search-title">
							uni-app
						</view>
						
					</view>
				</view>
			</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		}
	}
</script>
	
<style lang="scss">
	.navbar{
		width: 100%;
		.navbar-fixed{
			width: 100%;
			display: fixed;
			top: 0;
			left: 0;
			.navbar-content{
				display: flex;
				align-items: center;
				justify-content: center;
				width: 100%;
				height: 45px;
				background-color: $mk-base-color;
				padding: 0 15px;
				box-sizing: border-box;
				.navbar-search{
					width: 100%;
					height: 30px;
					background-color: #fff;
					border-radius: 15px;
					display: flex;
					align-items: center;
					padding: 0 15px;
					
					.navbar-search-icon{
						width: 15px;
						height: 15px;
						background-color: $mk-base-color;
					}
					.navbar-search-title{
						margin-left: 5px;
					}
				}
			}
		}
	}
	
	
</style>
