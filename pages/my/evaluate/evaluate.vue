<template>
	<view class="content">
		<view class="header">
			<view class="title">
				商品信息
			</view>
			<view class="mid">
				<image src="../../../static/goods%20(1).png" mode=""></image>
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
		</view>
		<view class="evaluate">
			<view class="title">
				描述相符
			</view>
			<uni-rate class="star" value="5" active-color="#FD4141" margin="11" size="27"></uni-rate>
			<view class="container">
				<textarea value="" placeholder="请输入宝贝评价"/>
				<view class="uploadBox" @tap="uploadImg" v-if="phto==''">
					<image src="../../../static/xiangj.png" mode=""></image>
					<view class="title">
						添加照片
					</view>
				</view>
				<view class="uploadBox" @tap="uploadImg"  v-if="phto!=''">
					<image :src="phto" mode=""></image>
				</view>
			</view>
		</view>
		<view class="bottomBtn">
			提交
		</view>
	</view>
</template>

<script>
	import uniRate from '@/components/uni-rate/uni-rate.vue'
	export default {
		components:{
			uniRate
		},
		data() {
			return {
				phto:''
			};
		},
		methods:{
			uploadImg(){
				uni.chooseImage({
				    success: (chooseImageRes) => {
				        const tempFilePaths = chooseImageRes.tempFilePaths;
						this.phto=tempFilePaths[0]
				    //     uni.uploadFile({
				    //         url: 'https://www.example.com/uploa', 
				    //         filePath: tempFilePaths[0],
				    //         name: 'file',
				    //         formData: {
				    //             'user': 'test'
				    //         },
				    //         success: (uploadFileRes) => {
								// let dataJS=JSON.parse(uploadFileRes.data)
								// if(dataJS.code==0){
								// 	uni.showToast({
								// 		title: '上传成功',
								// 		icon:'none',
								// 		duration:2000
								// 	});
								// }else{
								// 	uni.showToast({
								// 		title: '网络错误，请重试',
								// 		icon:'none',
								// 		duration:2000
								// 	});
								// }
				    //         }
				    //     });
				    }
				});
			}
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
			background: #FFFFFF;
			margin-top: 24upx;
			overflow: hidden;
			.title{
				margin: 32upx 0 0 20upx;
				font-size:30upx;
				font-family:PingFang;
				font-weight:bold;
				color:rgba(51,51,51,1);
			}
			.mid{
				display: flex;
				margin-top: 20upx;
				padding-bottom: 80upx;
				position: relative;
				image{
					width: 182upx;
					height: 182upx;
					margin-left:38upx;
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
					right: 55upx;
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
		}
		.evaluate{
			display: flex;
			padding-bottom: 220upx;
			flex-direction: column;
			align-items: center;
			background: #FFFFFF;
			margin-top: 10upx;
			overflow: hidden;
			.title{
				font-size:32upx;
				margin-top: 38upx;
				font-family:PingFang;
				font-weight:bold;
				color:rgba(51,51,51,1);
			}
			.star{
				margin-top: 50upx;
			}
			.container{
				margin-top: 76upx;
				width: 690upx;
				height: 300upx;
				background: #F8F8F8;
				textarea{
					margin: 20upx 20upx;
					width: 650upx;
					height: 80upx;
					font-size:22upx;
					font-family:HiraginoSansGB;
					font-weight:normal;
					color:rgba(153,153,153,1);
					line-height:38upx;
				}
				.uploadBox{
					position: absolute;
					margin-left: 20upx;
					image{
						width: 160upx;
						height: 160upx;
					}
					.title{
						position: absolute;
						margin-top: 0;
						left: 22upx;
						top: 100upx;
						font-size:28upx;
						font-family:HiraginoSansGB;
						font-weight:normal;
						color:rgba(153,153,153,1);
						line-height:28upx;
					}
				}
			}
		}
		.bottomBtn{
			width:750upx;
			height:80upx;
			line-height: 80upx;
			text-align: center;
			position: fixed;
			bottom: 0;
			background:rgba(255,83,83,1);
			font-size:34upx;
			font-family:PingFang;
			font-weight:bold;
			color:rgba(255,255,255,1);
		}
	}
</style>
