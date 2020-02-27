<template>
	<view class="content">
		<swiper :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000">
			<swiper-item>
				<view class="swiper-item">
					<image src="https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1582535872401&di=b87aae47656fde5459a0dcca761b4baa&imgtype=jpg&src=http%3A%2F%2Fimg0.imgtn.bdimg.com%2Fit%2Fu%3D1022058225%2C2669893653%26fm%3D214%26gp%3D0.jpg"
					 mode="aspectFill"></image>
				</view>
			</swiper-item>
			<swiper-item>
				<view class="swiper-item">
					<image src="https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1582535871786&di=c0eef9c32d014ea2c9ff632e883843d1&imgtype=0&src=http%3A%2F%2Fdpic.tiankong.com%2Fnd%2F55%2FQJ8520491215.jpg"
					 mode="aspectFill"></image>
				</view>
			</swiper-item>
			<swiper-item>
				<view class="swiper-item">
					<image src="https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=3362630969,1992340589&fm=26&gp=0.jpg" mode="aspectFill"></image>
				</view>
			</swiper-item>
		</swiper>
		<view class="goodsParameter">
			<view class="name">
				手工制！柏聆复古色民谣木吉他初学者学生男女初学入门41寸电箱
			</view>
			<view class="price">
				价格:￥5000
			</view>
			<view class="transport">
				<view class="item">
					快递:免费
				</view>
				<view class="item">
					月销:2000件
				</view>
				<view class="item">
					库存:200件
				</view>
			</view>
		</view>
		<view class="parameter">
			<view class="title">
				参数
			</view>
			<view class="itemBox">
				<view class="item">
					品牌名称：Abraham Joshua
				</view>
				<view class="item">
					产品参数：品牌: Abraham Joshua
				</view>
				<view class="item">
					型号: 星语心愿3.0
				</view>
				<view class="item">
					颜色分类: 白色，红色，黑色
				</view>
			</view>
		</view>
		<view class="details">
			<view class="title">
				商品详情
			</view>
			<image src="https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=3261994885,1034600030&fm=26&gp=0.jpg" mode="widthFix"></image>
			<image src="../../static/微信图片_20200227183518.jpg" mode="widthFix"></image>
		</view>
		<view class="evaluate">
			<view class="top">
				<view class="title">
					评价
				</view>
				<view class="more" @tap="goEvaluate">
					查看全部
					<image src="../../static/you.png" mode=""></image>
				</view>
			</view>
			<view class="container">
				<view class="one">
					<image src="https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=514937494,2212396255&fm=26&gp=0.jpg" mode=""></image>
					<view class="mid">
						<view class="name">
							koji
						</view>
						<view class="time">
							2019-08-09 13:00
						</view>
					</view>
					<uni-rate class="star" value="4" active-color="#FD4141" margin="7" size="16" disabled="true"></uni-rate>
				</view>
				<view class="txt">
					太棒了，老铁们赶紧上手，刚试了一下，真的太棒了音质特别好，刚刚到货弹唱了一首舒立生的“难道”
				</view>
				<view class="imgArr">
					<image src="https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=1720066558,4265907983&fm=26&gp=0.jpg" mode=""></image>
					<image src="https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=1457589487,4253534370&fm=26&gp=0.jpg" mode=""></image>
					<image src="https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=180474923,2591536205&fm=26&gp=0.jpg" mode=""></image>
				</view>
			</view>
		</view>
		<uni-popup ref="popup" type="bottom">
			<view class="Choice">
				<image class="close" @tap="close" src="../../static/close.png" mode=""></image>
				<view class="info">
					<image src="../../static/goods%20(1).png" mode=""></image>
					<view class="mid">
						<view class="name">
							手工制！柏聆复古色民谣木吉他初学者学生男女初学入门41寸电箱
						</view>
						<view class="Stock">
							库存132456件
						</view>
						<view class="color">
							选择颜色分类
						</view>
					</view>
				</view>
				<view class="nusm">
					<image src="../../static/delete.png" @tap="deleteNum" mode=""></image>
					<view class="Number">
						{{num}}
					</view>
					<image src="../../static/add.png" @tap="addNum" mode=""></image>
				</view>
				<view class="ChoiceItem">
					<view class="item">
						白色
					</view>
					<view class="item">
						白色
					</view>
					<view class="item">
						白色
					</view>
					<view class="item">
						白色
					</view>
					<view class="item">
						白色
					</view>
					<view class="item">
						白色
					</view>
				</view>
				<view class="btn" @tap="goOrder">
					确定
				</view>
			</view>
		</uni-popup>
		<view class="bottomBtn" @click="open">
			立即购买
		</view>
	</view>
</template>

<script>
	import uniRate from '@/components/uni-rate/uni-rate.vue'
	import uniPopup from "@/components/uni-popup/uni-popup.vue"
	export default {
		components: {
			uniRate,
			uniPopup
		},
		data() {
			return {
				num:1
			};
		},
		methods: {
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
			},
			open() {
				this.$refs.popup.open()
			},
			close(){
				this.$refs.popup.close()
			},
			goOrder() {
				uni.navigateTo({
					url: '../confirmationOrder/confirmationOrder',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			goEvaluate(){
				uni.navigateTo({
					url: '../evaluate/evaluate',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			}
		}
	}
</script>

<style lang="scss" scoped>
	.content {
		swiper {
			width: 100%;
			height: 500upx;

			image {
				width: 100%;
				height: 500upx;
			}
		}

		.goodsParameter {
			border-bottom: 2upx solid #F5F2F5;

			.name {
				font-size: 32upx;
				font-family: PingFang;
				font-weight: bold;
				color: rgba(51, 51, 51, 1);
				line-height: 39upx;
				margin: 22upx auto 0;
				width: 700upx;
			}

			.price {
				font-size: 30upx;
				font-family: PingFang;
				font-weight: bolder;
				margin: 28upx 0 0 20upx;
				color: rgba(255, 0, 0, 1);
				line-height: 30upx;
			}

			.transport {
				display: flex;
				justify-content: space-between;
				width: 700upx;
				margin: 40upx auto 0;

				.item {
					font-size: 24upx;
					font-family: PingFang;
					font-weight: 500;
					color: rgba(153, 153, 153, 1);
					line-height: 24upx;
					padding-bottom: 30upx;
				}
			}
		}

		.parameter {
			.title {
				font-size: 32upx;
				font-family: PingFang;
				font-weight: 500;
				color: rgba(51, 51, 51, 1);
				line-height: 32upx;
				margin: 24upx 0 0 20upx;
			}

			.itemBox {
				justify-content: space-between;
				padding: 24upx 20upx;
				margin-top: 24upx;
				background: #F6F6F6;
				display: flex;
				flex-wrap: wrap;
				font-size: 24upx;
				font-family: PingFang;
				font-weight: 500;
				color: rgba(51, 51, 51, 1);
				line-height: 36upx;
			}
		}

		.details {
			.title {
				font-size: 32upx;
				font-family: PingFang;
				font-weight: 500;
				color: rgba(51, 51, 51, 1);
				line-height: 32upx;
				margin: 24upx 0 0 20upx;
				padding-bottom: 24upx;
			}

			image {
				width: 100%;
			}
		}

		.evaluate {
			padding-bottom: 90upx;

			.top {
				display: flex;
				height: 80upx;
				line-height: 80upx;
				justify-content: space-between;
				border-bottom: 2upx solid #F5F2F5;

				.title {
					font-size: 32upx;
					font-family: PingFang;
					font-weight: 500;
					color: rgba(51, 51, 51, 1);
					margin-left: 20upx;
					// padding-bottom: 24upx;
				}

				.more {
					font-size: 24upx;
					font-family: PingFang;
					font-weight: 400;
					color: rgba(255, 0, 0, 1);
					margin-right: 20upx;

					image {
						width: 24upx;
						height: 20upx;
					}
				}
			}

			.container {
				.one {
					display: flex;
					position: relative;

					image {
						width: 74upx;
						height: 74upx;
						border-radius: 50%;
						margin: 18upx 0 0 20upx;
					}

					.mid {
						margin-left: 14upx;

						.name {
							margin-top: 10upx;
							font-size: 30upx;
							font-family: PingFang;
							font-weight: 400;
							color: rgba(51, 51, 51, 1);
							line-height: 30upx;
						}

						.time {
							font-size: 24upx;
							font-family: PingFang;
							font-weight: 400;
							color: rgba(51, 51, 51, 1);
							line-height: 24px;
							margin-top: 14upx;
						}
					}

					.star {
						// margin-left: 160upx;
						position: absolute;
						right: 32upx;
						top: 52upx;
					}
				}

				.txt {
					font-size: 24upx;
					font-family: PingFang;
					font-weight: 400;
					color: rgba(51, 51, 51, 1);
					line-height: 35upx;
					margin: 18upx 30upx 0 20upx;
				}

				.imgArr {
					display: flex;
					margin: 42upx auto 0;
					width: 710upx;
					justify-content: space-between;

					image {
						border-radius: 6upx;
						width: 190upx;
						height: 190upx;
					}
				}
			}
		}
		.Choice{
			background: #FFFFFF;
			border-top-right-radius: 40upx;
			border-top-left-radius: 40upx;
			.close{
				width: 50upx;
				height: 50upx;
				margin-top: 20upx;
				margin-left: 680upx;
			}
			.info{
				display: flex;
				margin-top: 32upx;
				image{
					width: 228upx;
					height: 228upx;
					margin-left: 20upx;
				}
				.mid{
					margin-left: 22upx;
					.name{
						font-size:32upx;
						width: 452upx;
						font-family:PingFang;
						font-weight:bold;
						color:rgba(51,51,51,1);
						line-height:39upx;
					}
					.Stock{
						font-size:24upx;
						font-family:PingFang;
						font-weight:400;
						color:rgba(153,153,153,1);
						line-height:24upx;
						margin-top: 10upx;
					}
					.color{
						font-size:24upx;
						font-family:PingFang;
						font-weight:400;
						color:rgba(51,51,51,1);
						line-height:24upx;
						margin-top: 22upx;
					}
				}
			}
			.nusm{
				display: flex;
				margin-left: 560upx;
				margin-top: 32upx;
				image{
					width: 50upx;
					height: 40upx;
				}
				.Number{
					padding: 0 28upx;
					font-size:32upx;
					font-family:PingFang;
					font-weight:400;
					color:rgba(153,153,153,1);
					line-height:40upx;
				}
			}
			.ChoiceItem{
				display: flex;
				width: 710upx;
				margin: 54upx auto 0;
				justify-content: space-between;
				flex-wrap: wrap;
				.item{
					width: 188upx;
					height: 76upx;
					border:2upx solid rgba(153,153,153,1);
					border-radius:10upx;
					text-align: center;
					line-height: 76upx;
					margin-bottom: 32upx;
				}
			}
			.btn{
				width:750upx;
				height:80upx;
				background:rgba(255,0,0,1);
				text-align: center;
				line-height: 80upx;
				font-size:36upx;
				font-family:PingFang;
				font-weight:bold;
				color:rgba(255,255,255,1);
			}
		}

		.bottomBtn {
			position: fixed;
			bottom: 0;
			width: 750upx;
			height: 80upx;
			background: rgba(255, 79, 75, 1);
			text-align: center;
			line-height: 80upx;
			font-size: 36upx;
			font-family: PingFang;
			font-weight: bold;
			color: rgba(255, 255, 255, 1);
		}
	}
</style>
