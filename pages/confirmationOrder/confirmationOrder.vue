<template>
	<view class="content">
		<view class="ads">
			<view class="title">
				收货地址
			</view>
			<view class="adsDetail">
				<image class="adsicon" src="../../static/ads.png" mode=""></image>
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
				<image class="you" src="../../static/you1.png" mode=""></image>
			</view>
		</view>
		<view class="goodsInfo">
			<view class="title">
				商品信息
			</view>
			<view class="item">
				<image src="../../static/goods.png" mode=""></image>
				<view class="name">
					雅集吉他新手大礼包
				</view>
				<view class="priceBox">
					<view class="price">
						￥399.00
					</view>
					<view class="numsBox">
						<view class="Symbol" @tap="deleteNum">
							➖
						</view>
						<view class="nums">
							{{num}}
						</view>
						<view class="Symbol" @tap="addNum">
							➕
						</view>
					</view>
				</view>
			</view>
		</view>
		<view class="bottomBtn">
			<view class="zj">
				<view class="title">
					共计：
				</view>
				<view class="price">
					￥1999
				</view>
			</view>
			<view class="btn" @tap="goDetaile">
				确认支付
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				num:1
			};
		},
		methods:{
			goDetaile(){
				uni.navigateTo({
					url: '../orderDetail/orderDetail',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			deleteNum(){
				if(this.num==1){
					uni.showToast({
						title: '不能再减了',
						icon:'none',
						duration:2000
					});
				}else{
					this.num--
				}
			},
			addNum(){
				this.num++
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
				justify-content: space-between;
				display: flex;
				.adsicon{
					width: 40upx;
					height: 48upx;
					margin-top: 40upx;
				}
				.mid{
					// margin-left: 24upx;
					padding-bottom: 44upx;
					.top{
						display: flex;
						font-size:32upx;
						font-family:PingFang;
						font-weight:bold;
						color:rgba(41,38,33,1);
						// line-height:319px;
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
		.goodsInfo{
			background: #FFFFFF;
			overflow: hidden;
			padding-bottom: 80upx;
			.title{
				font-size:30upx;
				font-family:PingFang;
				font-weight:bold;
				color:rgba(51,51,51,1);
				margin: 30upx 0 0 20upx;
			}
			.item{
				display: flex;
				margin-top: 18upx;
				position: relative;
				image{
					margin-left: 38upx;
					border-radius: 6upx;
					width: 182upx;
					height: 182upx;
				}
				.name{
					font-size:28upx;
					font-family:PingFang;
					font-weight:500;
					color:rgba(51,51,51,1);
					line-height:28upx;
					margin-left: 22upx;
					margin-top: 8upx;
				}
				.priceBox{
					font-size:30upx;
					font-family:PingFang;
					font-weight:500;
					color:rgba(51,51,51,1);
					line-height:30upx;
					position: absolute;
					top: 20upx;
					right: 54upx;
					.numsBox{
						margin-top: 20upx;
						display: flex;
						line-height: 30upx;
						.Symbol{
							border: 2upx solid #999999;
							border-radius: 50%;
						}
						.nums{
							padding: 0 20upx;
							font-size:24upx;
							font-family:PingFang;
							font-weight:500;
							color:rgba(51,51,51,1);
							// line-height:24upx;
							text-align: right;
						}
					}
				}
			}
		}
		.bottomBtn{
			position: fixed;
			justify-content: space-between;
			display: flex;
			bottom: 0;
			width:100%;
			height:80upx;
			line-height: 80upx;
			background:rgba(255,255,255,1);
			.zj{
				display: flex;
				.title{
					font-size:26upx;
					font-family:PingFang;
					font-weight:bold;
					color:rgba(51,51,51,1);
					margin-left: 40upx;
				}
				.price{
					font-size:32upx;
					font-family:PingFang;
					font-weight:bold;
					color:#FF0000;
				}
			}
			.btn{
				width:207upx;
				height:80upx;
				text-align: center;
				font-size:26upx;
				font-family:PingFang;
				font-weight:bold;
				color:rgba(255,255,255,1);
				background:rgba(255,79,75,1);
			}
		}
	}
</style>
