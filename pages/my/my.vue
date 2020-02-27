<template>
	<view class="content">
		<view class="header" @tap="goPersonalData">
			<image class="toux" src="https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=4227069332,3272640719&fm=11&gp=0.jpg" mode=""></image>
			<image class="renz" src="../../static/renz.png" mode=""></image>
			<view class="mid">
				<view class="name">
					昵称：工藤新一
				</view>
				<view class="gender">
					性别：男
				</view>
			</view>
			<image class="you" src="../../static/you2.png" mode=""></image>
		</view>
		<view class="navBox">
			<view class="top">
				<view class="title">
					全部订单
				</view>
				<view class="btn" @tap="goOrder(0)">
					查看所有订单
					<image src="../../static/you3.png" mode=""></image>
				</view>
			</view>
			<view class="bot">
				<view class="item" @tap="goOrder(1)">
					<image src="../../static/center_Pending%20payment@2x.png" mode=""></image>
					<view class="txt">
						待付款
					</view>
				</view>
				<view class="item" @tap="goOrder(2)">
					<image src="../../static/my%20(1).png" mode=""></image>
					<view class="txt">
						待发货
					</view>
				</view>
				<view class="item" @tap="goOrder(3)">
					<image src="../../static/my%20(3).png" mode=""></image>
					<view class="txt">
						待收货
					</view>
				</view>
				<view class="item" @tap="goOrder(4)">
					<image src="../../static/my%20(2).png" mode=""></image>
					<view class="txt">
						待评价
					</view>
				</view>
				<view class="item" @tap="goService">
					<image src="../../static/center_after%20sale@2x.png" mode=""></image>
					<view class="txt">
						退款/售后
					</view>
				</view>
			</view>
		</view>
		<view class="itemBox">
			<view class="item" @tap="goWallet">
				<image class="icon" src="../../static/my%20(5).png" mode=""></image>
				<view class="title">
					我的钱包
				</view>
				<image class="itemYou" src="../../static/you4.png" mode=""></image>
			</view>
			<view class="item" @tap="goShare">
				<image class="icon" src="../../static/my%20(11).png" mode=""></image>
				<view class="title">
					分享赚钱
				</view>
				<image class="itemYou" src="../../static/you4.png" mode=""></image>
			</view>
			<view class="item" @tap="goAuthentication">
				<image class="icon" src="../../static/my%20(7).png" mode=""></image>
				<view class="title">
					实名认证
				</view>
				<image class="itemYou" src="../../static/you4.png" mode=""></image>
			</view>
			<view class="item" @tap="goAddress">
				<image class="icon" src="../../static/my%20(6).png" mode=""></image>
				<view class="title">
					收货地址
				</view>
				<image class="itemYou" src="../../static/you4.png" mode=""></image>
			</view>
			<view class="item" @tap="goRebate">
				<image class="icon" src="../../static/my%20(8).png" mode=""></image>
				<view class="title">
					返利活动规则
				</view>
				<image class="itemYou" src="../../static/you4.png" mode=""></image>
			</view>
			<view class="item" @tap="goCustomerservice">
				<image class="icon" src="../../static/my%20(10).png" mode=""></image>
				<view class="title">
					联系客服
				</view>
				<image class="itemYou" src="../../static/you4.png" mode=""></image>
			</view>
			<view class="item" @tap="goAbout">
				<image class="icon" src="../../static/my%20(4).png" mode=""></image>
				<view class="title">
					关于我们
				</view>
				<image class="itemYou" src="../../static/you4.png" mode=""></image>
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
			goService(){
				uni.navigateTo({
					url: 'CustomerService/CustomerService',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			goOrder(id){
				uni.navigateTo({
					url: 'order/order?id='+id,
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			goCustomerservice(){
				uni.showToast({
					title: '客服打麻将去了，没在',
					icon:'none',
					duration:2000
				});
			},
			goPersonalData(){
				uni.navigateTo({
					url: 'personalData/personalData',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			goWallet(){
				uni.navigateTo({
					url: 'wallet/wallet',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			goShare(){
				uni.navigateTo({
					url: 'share/share',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			goAuthentication(){
				uni.navigateTo({
					url: 'Authentication/Authentication',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			goAddress(){
				uni.navigateTo({
					url: 'address/address',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			goRebate(){
				uni.navigateTo({
					url: 'Rebate/Rebate',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			goAbout(){
				uni.navigateTo({
					url: 'about/about',
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
		top: 0;
		left: 0;
		right: 0;
		bottom: 0;
		background: #F2F2F2;
		.header{
			width:750upx;
			height:315upx;
			display: flex;
			position: relative;
			background:linear-gradient(-45deg,rgba(3,187,219,1) 0%,rgba(3,211,233,1) 100%);
			.toux{
				width: 144upx;
				height: 144upx;
				border-radius: 50%;
				margin: 48upx 0 0 45upx;
			}
			.renz{
				width: 30upx;
				height: 30upx;
				position: absolute;
				top: 165upx;
				left: 140upx;
			}
			.mid{
				margin-left: 18upx;
				margin-top: 56upx;
				.name{
					font-size:32upx;
					font-family:PingFang;
					font-weight:bold;
					color:rgba(255,255,255,1);
					line-height:32upx;
				}
				.gender{
					font-size:26upx;
					font-family:PingFang;
					font-weight:400;
					color:rgba(255,255,255,1);
					line-height: 26upx;
					margin-top: 25upx;
				}
			}
			.you{
				width: 20upx;
				height: 30upx;
				margin-top: 100upx;
				position: absolute;
				right: 30upx;
			}
		}
		.navBox{
			// z-index: 1;
			position: relative;
			width:690upx;
			height:225upx;
			background:rgba(255,255,255,1);
			border-radius:40upx 40upx 0px 0px;
			margin: -94upx auto 0;
			.top{
				display: flex;
				height: 70upx;
				border-bottom: 2upx solid #F4F1F2;
				.title{
					font-size:31upx;
					font-family:Adobe Heiti Std;
					font-weight:normal;
					color:rgba(51,51,51,1);
					line-height:31upx;
					margin: 20upx 0 0 20upx;
				}
				.btn{
					margin-top: 30upx;
					font-size:20upx;
					font-family:PingFang;
					font-weight:400;
					color:rgba(3,201,227,1);
					line-height:20upx;
					position: absolute;
					right: 20upx;
					image{
						width: 20upx;
						height: 20upx;
					}
				}
			}
			.bot{
				display: flex;
				justify-content: space-around;
				.item{
					display: flex;
					margin-top: 34upx;
					// justify-content: center;
					flex-direction: column;
					align-items: center;
					image{
						width: 38upx;
						height: 38upx;
					}
					.txt{
						font-size:24upx;
						font-family:PingFang;
						font-weight:400;
						color:rgba(92,92,92,1);
						line-height:24upx;
						margin-top: 16upx;
					}
				}
			}
		}
		.itemBox{
			margin-top: 36upx;
			padding-bottom: 120upx;
			.item{
				display: flex;
				background: #FFFFFF;
				height: 80upx;
				align-items: center;
				border-bottom: 2upx solid #F6F3F7;
				.icon{
					width: 40upx;
					height: 40upx;
					margin-left: 20upx;
				}
				.title{
					margin-left: 22upx;
					font-size:30upx;
					font-family:PingFang;
					font-weight:400;
					color:rgba(51,51,51,1);
					line-height:30upx;
				}
				.itemYou{
					width:26upx;
					height:30upx;
					position: absolute;
					right: 30upx;
				}
			}
		}
	}
</style>
