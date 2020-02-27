<template>
	<view class="content">
		<view class="search">
			<image src="../../static/search.png" mode=""></image>
			<input type="text" value="" placeholder="请输入关键词"/>
		</view>
		<swiper :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000">
			<swiper-item>
				<view class="swiper-item">
					<image src="../../static/mao.jpg" mode=""></image>
				</view>
			</swiper-item>
			<swiper-item>
				<view class="swiper-item">
					<image src="https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=1916328458,329291841&fm=11&gp=0.jpg" mode="scaleToFill"></image>
				</view>
			</swiper-item>
			<swiper-item>
				<view class="swiper-item">
					<image src="https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1582809111718&di=4c5d9d1b352feb8845cdfa217cc1e99b&imgtype=0&src=http%3A%2F%2Fa0.att.hudong.com%2F61%2F00%2F31300543319869144533006129686.jpg" mode=""></image>
				</view>
			</swiper-item>
		</swiper>
		<view class="navBox">
			<view class="navItem" @tap="goGoodList">
				<image src="../../static/djc.png" mode=""></image>
				<view class="title">
					吉他·初级
				</view>
			</view>
			<view class="navItem" @tap="goGoodList">
				<image src="../../static/djz.png" mode=""></image>
				<view class="title">
					吉他·中级
				</view>
			</view>
			<view class="navItem" @tap="goGoodList">
				<image src="../../static/djg.png" mode=""></image>
				<view class="title">
					吉他·高级
				</view>
			</view>
		</view>
		<view class="newGoods">
			<view class="title">
				最新商品
			</view>
			<view class="goodsItem" @tap="goGoodList">
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
					<view class="btn">
						购买商品
					</view>
				</view>
			</view>
			<view class="goodsItem" @tap="goGoodList">
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
					<view class="btn">
						购买商品
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
				title: 'Hello'
			}
		},
		onLoad() {

		},
		methods: {
			goGoodList(){
				uni.navigateTo({
					url: '../goodList/goodList',
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
		.search{
			width:690upx;
			height:60upx;
			background:rgba(255,255,255,1);
			border-radius:30upx;
			margin: 25upx auto;
			display: flex;
			align-items: center;
			image{
				width: 30upx;
				height: 30upx;
				margin-left: 28upx;
			}
			input{
				margin-left: 17upx;
				font-size: 24upx;
			}
		}
		swiper{
			width:674upx;
			height:240upx;
			margin: 28upx auto;
			image{
				width:674upx;
				height:240upx;
			}
		}
		.navBox{
			display: flex;
			justify-content: space-around;
			.navItem{
				width: 220upx;
				height: 95upx;
				position: relative;
				.title{
					position: absolute;
					font-size:28upx;
					font-family:PingFang;
					font-weight:bold;
					color:rgba(255,255,255,1);
					line-height:96upx;
					left: 20upx;
				}
				image{
					position: absolute;
					top: 0;
					left: 0;
					width: 220upx;
					height: 95upx;
				}
			}
		}
		.newGoods{
			background: #FFFFFF;
			overflow: hidden;
			padding-bottom: 100upx;
			margin-top: 30upx;
			.title{
				font-size:36upx;
				font-family:PingFang;
				font-weight:bold;
				color:rgba(51,51,51,1);
				line-height:36upx;
				margin: 30upx 0 0 26upx;
				padding-bottom: 10upx;
			}
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
	}
</style>
