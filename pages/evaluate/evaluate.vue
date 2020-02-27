<template>
	<view class="content">
		<view class="navBox">
			<view class="item" :class="{active:show==0}" @tap="changeShow(0)">
				全部
			</view>
			<view class="item" :class="{active:show==1}" @tap="changeShow(1)">
				好评
			</view>
			<view class="item" :class="{active:show==2}" @tap="changeShow(2)">
				中评
			</view>
			<view class="item" :class="{active:show==3}" @tap="changeShow(3)">
				差评
			</view>
		</view>
		<view class="container">
			<view class="item" v-show="show==0||show==1">
				<view class="one">
					<image src="https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=3438376110,1833847425&fm=26&gp=0.jpg" mode=""></image>
					<view class="mid">
						<view class="name">
							koji
						</view>
						<view class="time">
							2019-08-09 13:00
						</view>
					</view>
					<uni-rate class="star" value="5" active-color="#FD4141" margin="7" size="16" disabled="true"></uni-rate>
				</view>
				<view class="txt">
					太棒了，老铁们赶紧上手，刚试了一下，真的太棒了音质特别好，刚刚到货弹唱了一首舒立生的“难道”
				</view>
				<view class="imgArr">
					<image src="https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=2894082503,679239847&fm=26&gp=0.jpg" mode=""></image>
					<image src="https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=2131289399,2296207160&fm=26&gp=0.jpg" mode=""></image>
					<image src="https://ss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=2218714435,1026696270&fm=26&gp=0.jpg" mode=""></image>
				</view>
			</view>
			<view class="item" v-show="show==0||show==2">
				<view class="one">
					<image src="http://img5.imgtn.bdimg.com/it/u=1993105234,1074032209&fm=26&gp=0.jpg" mode=""></image>
					<view class="mid">
						<view class="name">
							刘达
						</view>
						<view class="time">
							2019-08-09 13:00
						</view>
					</view>
					<uni-rate class="star" value="3" active-color="#FD4141" margin="7" size="16" disabled="true"></uni-rate>
				</view>
				<view class="txt">
					太一般了，我刘达作为一个灰常喜欢吉他的人觉得很一般
				</view>
				<view class="imgArr">
					<image src="https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=3783318111,4169817235&fm=26&gp=0.jpg" mode=""></image>
					<image src="https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=1788425415,885658163&fm=26&gp=0.jpg" mode=""></image>
					<image src="https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1582622455046&di=91e10e867c72e81733aadff5175c3a6e&imgtype=0&src=http%3A%2F%2Fb-ssl.duitang.com%2Fuploads%2Fitem%2F201611%2F14%2F20161114205056_SQfBE.thumb.700_0.jpeg" mode=""></image>
				</view>
			</view>
			<view class="item" v-show="show==0||show==3">
				<view class="one">
					<image src="http://img1.imgtn.bdimg.com/it/u=54550889,3842916716&fm=11&gp=0.jpg" mode=""></image>
					<view class="mid">
						<view class="name">
							隔壁老陈
						</view>
						<view class="time">
							2019-08-09 13:00
						</view>
					</view>
					<uni-rate class="star" value="1" active-color="#FD4141" margin="7" size="16" disabled="true"></uni-rate>
				</view>
				<view class="txt">
					太垃圾了，老铁们赶紧上手，刚试了一下，真的太棒了音质特别好，刚刚到货弹唱了一首舒立生的“难道”
				</view>
				<view class="imgArr">
					<image src="https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=1720066558,4265907983&fm=26&gp=0.jpg" mode=""></image>
					<image src="https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=1457589487,4253534370&fm=26&gp=0.jpg" mode=""></image>
					<image src="https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=180474923,2591536205&fm=26&gp=0.jpg" mode=""></image>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	import uniRate from '@/components/uni-rate/uni-rate.vue'
	export default {
		components: {
			uniRate
		},
		data() {
			return {
				show:0
			};
		},
		methods:{
			changeShow(e){
				this.show=e
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
		background: #F7F7F5;
		.navBox{
			background: #FFFFFF;
			display: flex;
			margin-top: 10upx;
			height: 80upx;
			align-items: center;
			.item{
				margin-left: 20upx;
				width:100upx;
				height:47upx;
				border:2upx solid rgba(153,153,153,1);
				border-radius:24upx;
				text-align: center;
				line-height: 47upx;
				font-size:24upx;
				font-family:PingFang;
				font-weight:400;
				color:rgba(153,153,153,1);
			}
			.active{
				color: #333333;
				border-color: #333333;
			}
		}
		.container {
			background: #FFFFFF;
			margin-top: 10upx;
			.item{
				padding-bottom: 26upx;
				border-bottom: 2upx solid #F6F5F8;
			}
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
</style>
