<template>
	<view class="content">
		<view class="order">
			<view class="top">
				<view class="orderNum">
					订单号：8208208820
				</view>
			</view>
			<view class="mid">
				<image src="../../../static/goods%20(1).png" mode=""></image>
				<view class="name">
					雅集吉他新手大礼包
				</view>
				<view class="priceBox">
					<view class="price">
						￥399.00
					</view>
					<view class="nums">
						×1
					</view>
				</view>
			</view>
			<view class="total">
				共1件商品  合计：<view class="totalPrice">￥399.00</view>
			</view>
			<view class="status">
				退款成功 退款成功￥399.00
			</view>
			<view class="btnBox" @tap="goDetaile">
				<view class="item">
					查看详情
				</view>
			</view>
		</view>
		<view class="order">
			<view class="top">
				<view class="orderNum">
					订单号：8208208820
				</view>
			</view>
			<view class="mid">
				<image src="../../../static/goods%20(1).png" mode=""></image>
				<view class="name">
					雅集吉他新手大礼包
				</view>
				<view class="priceBox">
					<view class="price">
						￥399.00
					</view>
					<view class="nums">
						×1
					</view>
				</view>
			</view>
			<view class="total">
				共1件商品  合计：<view class="totalPrice">￥399.00</view>
			</view>
			<view class="status">
				换货成功
			</view>
			<view class="btnBox">
				<view class="item" @tap="goExchange">
					查看详情
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
			goDetaile(){
				uni.navigateTo({
					url: '../RefundDetails/RefundDetails',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			goExchange(){
				uni.navigateTo({
					url: '../exchangeDetails/exchangeDetails',
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
		height:auto!important;
		min-height:100vh;
		background: #F2F2F2;
		overflow: hidden;
		.order{
			background: #FFFFFF;
			width: 700upx;
			margin: 16upx auto 0;
			border-radius: 20upx;
			position: relative;
			padding-bottom: 146upx;
			.top{
				display: flex;
				justify-content: space-between;
				.orderNum{
					font-size:36upx;
					font-family:PingFang;
					font-weight:bold;
					color:rgba(51,51,51,1);
					line-height:36upx;
					margin-top: 20upx;
					margin-left: 26upx;
				}
				.status{
					font-size:24upx;
					font-family:PingFang;
					font-weight:400;
					color:rgba(51,51,51,1);
					line-height:24upx;
					margin: 20upx 20upx 0 0;
				}
			}
			.mid{
				display: flex;
				margin-top: 40upx;
				position: relative;
				image{
					width: 182upx;
					height: 182upx;
					margin-left:14upx;
					
				}
				.name{
					font-size:28upx;
					font-family:PingFang;
					font-weight:500;
					color:rgba(51,51,51,1);
					line-height:28px;
					margin: 6upx 0 0 28upx;
				}
				.priceBox{
					position: absolute;
					right: 22upx;
					top: 20upx;
					font-size:30upx;
					font-family:PingFang;
					font-weight:500;
					color:rgba(51,51,51,1);
					line-height:30upx;
					.nums{
						font-size:24upx;
						font-family:PingFang;
						font-weight:500;
						color:rgba(51,51,51,1);
						line-height:24upx;
						text-align: right;
						margin-top: 16upx;
					}
				}
			}
			.total{
				font-size:26upx;
				font-family:PingFang;
				font-weight:500;
				color:rgba(51,51,51,1);
				line-height:26upx;
				display: flex;
				position: absolute;
				right: 24upx;
				top: 252upx;
			}
			.status{
				width:604upx;
				height:80upx;
				margin: 32upx auto 0;
				background:rgba(241,241,241,1);
				border-radius:10upx;
				line-height: 80upx;
				padding-left: 30upx;
				font-size:26upx;
				font-family:PingFang;
				font-weight:500;
				color:rgba(51,51,51,1);
			}
			.btnBox{
				display: flex;
				margin-top: 52upx;
				position: absolute;
				right: 24upx;
				// margin-left: 310upx;
				.item{
					margin-right: 20upx;
					text-align: center;
					line-height: 60upx;
					width:172upx;
					height:60upx;
					border:1upx solid rgba(214,214,214,1);
					border-radius:28upx;
					font-size:24upx;
					font-family:PingFang;
					font-weight:400;
					color:rgba(153,153,153,1);
				}
			}
		}
	}
</style>
