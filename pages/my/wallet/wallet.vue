<template>
	<view class="content">
		<view class="top">
			<view class="title">
				我的余额
			</view>
			<view class="num">
				999.99
			</view>
			<view class="btn" @tap="goCash">
				提现
			</view>
		</view>
		<view class="listItem">
			<view class="title">
				明细
			</view>
			<view class="item">
				<view class="left">
					<view class="Itemtitle">
						提现
					</view>
					<view class="time">
						2019-08-09
					</view>
				</view>
				<view class="right">
					-￥500
				</view>
			</view>
			<view class="item">
				<view class="left">
					<view class="Itemtitle">
						提现
					</view>
					<view class="time">
						2019-08-09
					</view>
				</view>
				<view class="right">
					-￥500
				</view>
			</view>
			<view class="item">
				<view class="left">
					<view class="Itemtitle">
						提现
					</view>
					<view class="time">
						2019-08-09
					</view>
				</view>
				<view class="right">
					-￥500
				</view>
			</view>
			<view class="item" :class="{active:id==4}">
				<view class="left">
					<view class="Itemtitle">
						提现失败
					</view>
					<view class="time">
						2019-08-09
					</view>
				</view>
				<view class="right" v-if="id!=4">
					-￥500
				</view>
				<view class="btnItem" v-if="id==4" @tap="goDetaile">
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
				id:4
			};
		},
		methods:{
			goDetaile(){
				uni.navigateTo({
					url: 'reasonsForFailure/reasonsForFailure',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			goCash(){
				uni.navigateTo({
					url: 'cash/cash',
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
		right: 0;
		top: 0;
		bottom: 0;
		background: #F1F1F1;
		.top{
			width: 100%;
			height: 400upx;
			display: flex;
			align-items: center;
			// justify-content: center;
			flex-direction: column;
			background:linear-gradient(-45deg,rgba(3,187,219,1) 0%,rgba(3,211,233,1) 100%);
			.title{
				font-size:30upx;
				font-family:PingFang;
				font-weight:400;
				color:rgba(255,255,255,1);
				line-height:30upx;
				margin-top: 120upx;
			}
			.num{
				font-size: 60upx;
				color: #FFFFFF;
				font-weight: bold;
				margin-top: 10upx;
			}
			.btn{
				margin-top: 40upx;
				width:197upx;
				height:80upx;
				background:rgba(255,255,255,1);
				border-radius:40upx;
				text-align: center;
				line-height: 80upx;
				font-size:32upx;
				font-family:PingFang;
				font-weight:bold;
				color:rgba(3,187,219,1);
			}
		}
		.listItem{
			margin-top: 20upx;
			.title{
				font-size:30upx;
				font-family:PingFang;
				font-weight:bold;
				color:rgba(51,51,51,1);
				line-height:80upx;
				background: #FFFFFF;
				padding-left: 20upx;
			}
			.item{
				background: #FFFFFF;
				display: flex;
				height: 98upx;
				justify-content: space-between;
				padding: 0 20upx;
				border-top: 2upx solid #F4F1F4;
				.Itemtitle{
					font-size:26upx;
					font-family:PingFang;
					font-weight:bold;
					// color:rgba(51,51,51,1);
					line-height:26upx;
					margin-top: 16upx;
				}
				.time{
					font-size:20upx;
					font-family:PingFang;
					font-weight:400;
					// color:rgba(51,51,51,1);
					line-height:20upx;
					margin-top: 22upx;
				}
				.right{
					line-height: 98upx;
					font-size:30upx;
					font-family:PingFang;
					font-weight:400;
					// color:rgba(51,51,51,1);
				}
				.btnItem{
					font-size:22upx;
					font-family:PingFang;
					font-weight:400;
					line-height: 98upx;
					color:rgba(255,0,0,1);
				}
			}
			.active{
				color: #FF0000!important;
			}
		}
	}
</style>
