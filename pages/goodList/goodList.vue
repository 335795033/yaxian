<template>
	<view class="content">
		<view class="goodsItem">
			<view class="img">
				<image src="../../static/goods.png" mode=""></image>
			</view>
			<view class="txt">
				<view class="name">
					单板吉他41寸民谣面单木吉他初学者新手练习吉他
				</view>
				<view class="priceBox">
					<view class="price">
						￥899
					</view>
					<view class="amount">
						199人付款
					</view>
				</view>
				<view class="btn" @tap="goDetails">
					购买商品
				</view>
			</view>
		</view>
		<view class="goodsItem">
			<view class="img">
				<image src="../../static/goods.png" mode=""></image>
			</view>
			<view class="txt">
				<view class="name">
					单板吉他41寸民谣面单木吉他初学者新手练习吉他
				</view>
				<view class="priceBox">
					<view class="price">
						￥899
					</view>
					<view class="amount">
						199人付款
					</view>
				</view>
				<view class="btn" @tap="goDetails">
					购买商品
				</view>
			</view>
		</view>
		<view class="goodsItem">
			<view class="img">
				<image src="../../static/goods.png" mode=""></image>
			</view>
			<view class="txt">
				<view class="name">
					单板吉他41寸民谣面单木吉他初学者新手练习吉他
				</view>
				<view class="priceBox">
					<view class="price">
						￥899
					</view>
					<view class="amount">
						199人付款
					</view>
				</view>
				<view class="btn" @tap="goDetails">
					购买商品
				</view>
			</view>
		</view>
		<view class="goodsItem">
			<view class="img">
				<image src="../../static/goods.png" mode=""></image>
			</view>
			<view class="txt">
				<view class="name">
					单板吉他41寸民谣面单木吉他初学者新手练习吉他
				</view>
				<view class="priceBox">
					<view class="price">
						￥899
					</view>
					<view class="amount">
						199人付款
					</view>
				</view>
				<view class="btn" @tap="goDetails">
					购买商品
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
		},
		methods:{
			goDetails(){
				uni.navigateTo({
					url: '../goodsDetails/goodsDetails',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			}
		}
	}
</script>

<style lang="scss" scoped>
	.content{
		.goodsItem{
			display: flex;
			margin-top: 30upx;
			.img{
				margin-left: 26upx;
				width: 292upx;
				height: 292upx;
				border-radius: 10upx;
				image{
					width: 292upx;
					height: 292upx;
					border-radius: 10upx;
				}
			}
			.txt{
				margin-left: 24upx;
				.name{
					font-size:30upx;
					font-family:PingFang;
					font-weight:400;
					color:rgba(51,51,51,1);
					line-height:38upx;
					width: 364upx;
					margin-top: 20upx;
				}
				.priceBox{
					display: flex;
					margin-top: 76upx;
					.price{
						font-size:36upx;
						font-family:PingFang;
						font-weight:bold;
						color:rgba(255,79,75,1);
						line-height:36upx;
					}
					.amount{
						font-size:24upx;
						font-family:PingFang;
						font-weight:400;
						margin-left: 22upx;
						color:rgba(184,184,184,1);
						line-height:24upx;
					}
				}
				.btn{
					width:208upx;
					height:60upx;
					background:rgba(255,79,75,1);
					border-radius:30upx;
					font-size:24upx;
					font-family:PingFang;
					font-weight:bold;
					color:rgba(255,255,255,1);
					line-height:60upx;
					text-align: center;
					margin:40upx 0 0 170upx;
				}
			}
		}
	}
</style>
