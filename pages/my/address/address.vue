<template>
	<view class="content">
		<view class="container">
			<view class="item">
				<view class="top">
					<view class="name">
						王哥哥
					</view>
					<view class="phone">
						8008008820
					</view>
				</view>
				<view class="address">
					北京市  北京市  朝阳区  花园路甲220号花园路甲25号写字楼230室  
				</view>
				<view class="bottom">
					<image class="seclet" v-if="show!=1" src="../../../static/weixuanz.png" mode=""></image>
					<image class="seclet" v-if="show==1" src="../../../static/xuanzhong.png" mode=""></image>
					<view class="title" v-if="show!=1">
						设为默认
					</view>
					<view class="title" v-if="show==1" style="color: #FF6262;">
						已设为默认
					</view>
					<view class="btnBox">
						<view class="btn">
							<image src="../../../static/ads%20(2).png" mode=""></image>
							<view class="btnTitle">
								编辑
							</view>
						</view>
						<view class="btn">
							<image src="../../../static/ads%20(1).png" mode=""></image>
							<view class="btnTitle">
								删除
							</view>
						</view>
					</view>
				</view>
			</view>
			<view class="item">
				<view class="top">
					<view class="name">
						王哥哥
					</view>
					<view class="phone">
						8008008820
					</view>
				</view>
				<view class="address">
					北京市  北京市  朝阳区  花园路甲220号花园路甲25号写字楼230室  
				</view>
				<view class="bottom">
					<image class="seclet" v-if="show!=2" src="../../../static/weixuanz.png" mode=""></image>
					<image class="seclet" v-if="show==2" src="../../../static/xuanzhong.png" mode=""></image>
					<view class="title" v-if="show!=2">
						设为默认
					</view>
					<view class="title" v-if="show==2" style="color: #FF6262;">
						已设为默认
					</view>
					<view class="btnBox">
						<view class="btn">
							<image src="../../../static/ads%20(2).png" mode=""></image>
							<view class="btnTitle">
								编辑
							</view>
						</view>
						<view class="btn">
							<image src="../../../static/ads%20(1).png" mode=""></image>
							<view class="btnTitle">
								删除
							</view>
						</view>
					</view>
				</view>
			</view>
			<view class="bottomBtn" @tap="goAdd">
				新增收货地址
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				show:1
			};
		},
		methods:{
			goAdd(){
				uni.navigateTo({
					url: 'addAddress/addAddress',
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
		bottom: 0;
		top: 0;
		background: #F8F8F8;
		.container{
			.item{
				border-top: 2upx solid #F8F8F8;
				margin-bottom: 20upx;
				background: #FFFFFF;
				.top{
					display: flex;
					font-size:32upx;
					font-family:PingFang;
					font-weight:bold;
					color:rgba(41,38,33,1);
					line-height:32upx;
					.name{
						margin: 28upx 0 0 28upx;
					}
					.phone{
						font-size:28upx;
						line-height: 28upx;
						margin: 28upx 0 0 28upx;
					}
				}
				.address{
					font-size:28upx;
					font-family:PingFang;
					font-weight:500;
					color:rgba(41,38,33,1);
					line-height:36upx;
					width: 580upx;
					margin: 20upx 0 0 30upx;
					padding-bottom: 38upx;
					// border-bottom: 2upx solid #F1F1F1;
				}
				.bottom{
					display: flex;
					height: 80upx;
					align-items: center;
					border-top: 2upx solid #F1F1F1;
					image{
						width: 30upx;
						height: 30upx;
					}
					.seclet{
						margin-left: 30upx;
					}
					.title{
						font-size:24upx;
						font-family:PingFang;
						font-weight:500;
						color:rgba(138,133,124,1);
						// line-height:24upx;
						margin-left: 10upx;
					}
					.btnBox{
						display: flex;
						position: absolute;
						right: 30upx;
					}
					.btn{
						display: flex;
						margin-left: 32upx;
						.btnTitle{
							margin-left: 8upx;
							font-size:24upx;
							font-family:PingFang;
							font-weight:500;
							color:rgba(138,133,124,1);
							// line-height:24upx;
						}
					}
				}
			}
			.bottomBtn{
				width:750Upx;
				height:98Upx;
				background:rgba(255,83,83,1);
				text-align: center;
				line-height: 98upx;
				position: fixed;
				bottom: 0;
				font-size:34upx;
				font-family:PingFang;
				font-weight:bold;
				color:rgba(255,255,255,1);
			}
		}
	}
</style>
