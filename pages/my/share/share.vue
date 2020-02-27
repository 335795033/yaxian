<template>
	<view class="content">
		<view class="container">
			<view class="bai">
				<image class="kuang" src="../../../static/kuang.png" mode=""></image>
				<image class="ewm" src="../../../static/ewm.png" mode=""></image>
				<view class="btnBox">
					<view class="item">
						申请代理商
					</view>
					<view class="item">
						分享好友
					</view>
				</view>
			</view>
			<view class="bottom">
				<view class="title">
					活动规则
				</view>
				<view class="txt">
					击分享，将你喜欢的商品、专题文章通过微信等社交媒体分享给小伙伴，当好友通过你分享的链接进入豌豆公主并下单，你和好友都会获得与该订单总金额相等的积分。如果你的好友是首次在豌豆公主下单，你将会获得该订单总金额的双倍积分。友通过你分享的链接首次在豌豆公主下单，订单金额为200元，你将会获得400积分；
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

<style lang="scss" scoped>
	.content{
		position: absolute;
		left: 0;
		top: 0;
		right: 0;
		bottom: 0;
		background: url('http://inews.gtimg.com/newsapp_bt/0/11237088946/1000.jpg');
		background-size: 100% 100%;
		.container{
			.bai{
				width: 635upx;
				height: 800upx;
				margin: 40upx auto 0;
				position: relative;
				background: rgba($color: #fff, $alpha: .6);
				.kuang{
					width: 470upx;
					height: 470upx;
					margin: 118upx 83upx 0 83upx;
				}
				.ewm{
					width: 328upx;
					height: 328upx;
					position: absolute;
					left: 150upx;
					top: 188upx;
				}
				.btnBox{
					display: flex;
					justify-content: space-around;
					margin-top: 66upx;
					.item{
						text-align: center;
						line-height: 74upx;
						width:204upx;
						height:74upx;
						background:rgba(3,187,220,1);
						border-radius:37upx;
						font-size:24upx;
						font-family:PingFang;
						font-weight:400;
						color:rgba(255,255,255,1);
					}
				}
			}
			.bottom{
				// margin-top: 30upx;
				position: fixed;
				bottom: 0;
				background: #FFFFFF;
				overflow: hidden;
				.title{
					font-size:30upx;
					font-family:PingFang;
					font-weight:bold;
					color:rgba(51,51,51,1);
					line-height:40upx;
					margin: 24upx 0 0 20upx;
				}
				.txt{
					padding: 24upx;
					font-size:24upx;
					font-family:PingFang;
					// font-weight:bold;
					color:#999999;
					line-height:40upx;
				}
			}
		}
	}
</style>
