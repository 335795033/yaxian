<template>
	<view class="content">
		<view class="ads">
			<view class="title">
				收货地址
			</view>
			<view class="adsDetail">
				<image class="adsicon" src="../../../../static/ads.png" mode=""></image>
				<view class="mid">
					<view class="top">
						<view class="name">
							春春儿
						</view>
						<view class="phone">
							9090900
						</view>
					</view>
					<view class="address">
						 北京市  北京市  朝阳区  花园路甲220号花园路甲25号写字楼230室  
					</view>
				</view>
			</view>
		</view>
		<view class="order">
			<view class="top">
				<view class="orderNum">
					订单号：8208208820
				</view>
				<view class="status">
					2019-09-08 13:00
				</view>
			</view>
			<view class="mid">
				<image src="../../../../static/goods%20(1).png" mode=""></image>
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
			<view class="btnBox" v-if="type==1">
				<view class="item">
					取消订单
				</view>
			</view>
			<view class="btnBox" v-if="type==2">
				<view class="item">
					提醒发货
				</view>
			</view>
			<view class="btnBox" v-if="type==3">
				<view class="item" @tap="goRefund">
					退货
				</view>
				<view class="item" @tap="goExchange">
					换货
				</view>
				<view class="item">
					确认收货
				</view>
			</view>
			<view class="btnBox" v-if="type==4">
				<view class="item" @tap="goRefund">
					退货
				</view>
				<view class="item" @tap="goExchange">
					换货
				</view>
				<view class="item" @tap="goEvaluat">
					去评价
				</view>
			</view>
		</view>
		<view class="logistics" v-if="type==3||type==4">
			<view class="title">
				物流信息
			</view>
			<view class="container">
				暂无
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				type:1
			};
		},
		onLoad(e) {
			this.type=e.type
		},
		methods:{
			goRefund(){
				uni.navigateTo({
					url: '../Refund/Refund',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			goExchange(){
				uni.navigateTo({
					url: '../Exchange/Exchange',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			goEvaluat(){
				uni.navigateTo({
					url: '../../evaluate/evaluate',
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
		position: absolute;
		left: 0;
		top: 0;
		right: 0;
		bottom: 0;
		background: #F1F1F1;
		.ads{
			border-bottom: 2upx solid #F5F3F3;
			background: #FFFFFF;
			overflow: hidden;
			margin-top: 24upx;
			.title{
				font-size:30upx;
				margin:30upx 0 0 20upx;
				font-family:PingFang;
				font-weight:bold;
				color:rgba(51,51,51,1);
			}
			.adsDetail{
				width: 710upx;
				margin:38upx auto 0;
				display: flex;
				.adsicon{
					width: 40upx;
					height: 48upx;
					margin-top: 40upx;
				}
				.mid{
					margin-left: 24upx;
					padding-bottom: 44upx;
					.top{
						display: flex;
						font-size:32upx;
						font-family:PingFang;
						font-weight:bold;
						color:rgba(41,38,33,1);
						width: 310upx;
						justify-content: space-between;
					}
					.address{
						margin-top: 18upx;
						font-size:28upx;
						width: 580upx;
						font-family:PingFang;
						font-weight:500;
						color:rgba(41,38,33,1);
						line-height:32upx;
					}
				}
				.you{
					width:40upx;
					height:36upx;
					margin-top: 40upx;
				}
			}
		}
		.order{
			background: #FFFFFF;
			width: 700upx;
			margin: 16upx auto 0;
			border-radius: 20upx;
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
				margin: 48upx 0 0 334upx;
			}
			.btnBox{
				display: flex;
				margin-top: 52upx;
				position: absolute;
				right: 26upx;
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
		.logistics{
			background: #FFFFFF;
			margin-top: 20upx;
			overflow: hidden;
			.title{
				font-size:32upx;
				font-family:PingFang;
				font-weight:bold;
				color:rgba(51,51,51,1);
				line-height:48upx;
				margin: 30upx 0 0 20upx;
			}
			.container{
				font-size:32upx;
				font-family:PingFang;
				font-weight:bold;
				color:rgba(51,51,51,1);
				line-height:48upx;
				margin: 30upx 0 0 20upx;
			}
		}
	}
</style>
