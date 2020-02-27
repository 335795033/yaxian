<template>
	<view class="content">
		<view class="header">
			<view class="status" v-if="status==4" style="background: #FF0000;">
				换货失败
			</view>
			<view class="status" v-if="status==3">
				换货成功
			</view>
			<view class="status" v-if="status==2">
				换货中
			</view>
			<view class="status" v-if="status==1">
				审核中
			</view>
			<view class="status" v-if="status==0">
				待审核
			</view>
			<view class="time">
				2017年10月31日   14：28
			</view>
		</view>
		<view class="progress">
			<view class="length" :style="widthS"></view>
			<view class="top" v-if="status==0">
				<view class="yuan" style="background:#03BBDB"></view>
				<view class="yuan"></view>
				<view class="yuan"></view>
				<view class="yuan"></view>
			</view>
			<view class="top" v-if="status==1">
				<view class="yuan" style="background:#03BBDB"></view>
				<view class="yuan" style="background:#03BBDB"></view>
				<view class="yuan"></view>
				<view class="yuan"></view>
			</view>
			<view class="top" v-if="status==2">
				<view class="yuan" style="background:#03BBDB"></view>
				<view class="yuan" style="background:#03BBDB"></view>
				<view class="yuan" style="background:#03BBDB"></view>
				<view class="yuan"></view>
			</view>
			<view class="top" v-if="status==3">
				<view class="yuan" style="background:#03BBDB"></view>
				<view class="yuan" style="background:#03BBDB"></view>
				<view class="yuan" style="background:#03BBDB"></view>
				<view class="yuan" style="background:#03BBDB"></view>
			</view>
			<view class="bot">
				<view class="item">待审核</view>
				<view class="item">审核中</view>
				<view class="item">换货中</view>
				<view class="item">已完成</view>
			</view>
		</view>
		<view class="info">
			换货信息
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
				<image src="../../../static/goods%20(1).png" mode=""></image>
				<view class="name">
					雅集吉他新手大礼包
				</view>
				<view class="priceBoxS">
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
		</view>
		<view class="Reason">
			<view class="item">
				退款原因：不喜欢/不想要
			</view>
			<view class="item">
				退款金额：¥139.00
			</view>
			<view class="item">
				申请时间：2017-10-30  19:22
			</view>
			<view class="item">
				退款说明：
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				status:3,
				widthS:{'width':'206upx'}
			};
		},
		onLoad() {
			this.widthS.width=this.status*206+'upx'
		}
	}
</script>

<style lang="scss" scoped>
	.content{
		height:auto!important;
		min-height:100vh;
		background: #F2F2F2;
		overflow: hidden;
		.header{
			width:750upx;
			height:184upx;
			background:rgba(3,187,219,1);
			overflow: hidden;
			.status{
				font-size:32upx;
				font-family:PingFang;
				font-weight:bold;
				color:rgba(255,255,255,1);
				line-height:32upx;
				margin: 60upx 0 0 78upx;
			}
			.time{
				font-size:24upx;
				font-family:PingFang;
				font-weight:500;
				color:rgba(234,234,234,1);
				line-height:24upx;
				margin: 22upx 0 0 78upx;
			}
		}
		.progress{
			width: 100%;
			// height: 178upx;
			position: relative;
			.length{
				position: absolute;
				top: 0upx;
				left: 67upx;
				width: 20upx;
				height: 6upx;
				background: #03BBDB;
			}
			.top{
				margin: 68upx auto 6upx;
				width: 620upx;
				border-top: 6upx solid #999999;
				display: flex;
				justify-content: space-between;
				.yuan{
					position: relative;
					top: -12upx;
					width:20upx;
					height:20upx;
					background:#999999;
					border-radius:50%;
				}
			}
			.bot{
				display: flex;
				margin:0 44upx;
				justify-content: space-between;
				font-size:24upx;
				font-family:PingFang;
				font-weight:500;
				color:rgba(102,102,102,1);
			}
		}
		.info{
			width:750upx;
			height:90upx;
			background:rgba(255,255,255,1);
			box-shadow:0upx -1upx 0upx 0upx rgba(240,240,240,1);
			font-size:28upx;
			line-height: 90upx;
			padding-left: 24upx;
			margin-top: 48upx;
			font-family:PingFang;
			font-weight:500;
			color:rgba(51,51,51,1);
		}
		.order{
			background: #FFFFFF;
			width: 700upx;
			margin: 16upx auto 0;
			border-radius: 20upx;
			padding-bottom: 78upx;
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
				.priceBoxS{
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
		}
		.Reason{
			// position: fixed;
			// bottom: 0;
			background: #FFFFFF;
			margin-top: 20upx;
			font-size:24upx;
			font-family:PingFang;
			font-weight:500;
			color:rgba(153,153,153,1);
			width: 100%;
			padding: 28upx 0 0 24upx;
		}
	}
</style>
