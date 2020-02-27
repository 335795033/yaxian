<template>
	<view class="content">
		<view class="header">
			<view class="title">
				提现金额
			</view>
			<view class="price">
				￥<input type="text" value="" placeholder="输入提现金额"/>
			</view>
			<view class="tips">
				<view class="title">
					可提现5000.00
				</view>
				<view class="btn">
					全部提现
				</view>
			</view>
		</view>
		<view class="Apply">
			<view class="top">
				<view class="title">
					提现申请
				</view>
				<image src="../../../../static/wenhao.png" mode="" @tap="goExplain"></image>
			</view>
			<view class="upload" v-if="phto==''" @tap="uploadImg">
				<image src="../../../../static/xiangj.png" mode=""></image>
				<view class="text">
					添加图片
				</view>
			</view>
			<image class="uploadimg" :src="phto" v-if="phto!=''" mode="" @tap="uploadImg"></image>
		</view>
		<view class="bottomBtn">
			提交
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				phto:''
			};
		},
		methods:{
			goExplain(){
				uni.navigateTo({
					url: 'cashExplain/cashExplain',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
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
		position: absolute;
		left: 0;
		right: 0;
		top: 0;
		bottom: 0;
		background: #F1F1F1;
		.header{
			background: #FFFFFF;
			overflow: hidden;
			margin-top: 20upx;
			.title{
				margin: 36upx 0 0 20upx;
				font-size:34upx;
				font-family:PingFang;
				font-weight:bold;
				color:rgba(51,51,51,1);
			}
			.price{
				display: flex;
				margin: 50upx 0 0 20upx;
				padding-bottom: 18upx;
				font-size:50upx;
				font-family:PingFang;
				font-weight:bold;
				color:rgba(51,51,51,1);
				input{
					font-size: 50upx;
					line-height: 50upx;
					font-weight: normal;
				}
			}
			.tips{
				display: flex;
				border-top: 2upx solid #F1F1F1;
				height: 64upx;
				align-items: center;
				justify-content: space-between;
				.title{
					margin:0 0 0 20upx;
					font-size:24upx;
					font-family:PingFang;
					font-weight:bold;
					color:rgba(255,0,0,1);
				}
				.btn{
					margin-right: 20upx;
					font-size:24upx;
					font-family:PingFang;
					font-weight:400;
					color:rgba(3,187,219,1);
				}
			}
		}
		.Apply{
			background: #FFFFFF;
			margin-top: 20upx;
			padding-bottom: 72upx;
			.top{
				display: flex;
				.title{
					margin: 40upx 0 0 20upx;
					font-size:34upx;
					font-family:PingFang;
					font-weight:bold;
					color:rgba(38,25,0,1);
				}
				image{
					width: 36upx;
					height: 36upx;
					margin: 42upx 0 0 10upx;
				}
			}
			.upload{
				position: relative;
				margin: 82upx 0 0 20upx;
				image{
					width: 160upx;
					height: 160upx;
				}
				.text{
					position: absolute;
					font-size:24upx;
					font-family:PingFang;
					font-weight:bold;
					left: 32upx;
					top: 104upx;
					color:rgba(191,191,191,1);
				}
			}
			.uploadimg{
				margin: 82upx 0 0 20upx;
				width: 160upx;
				height: 160upx;
			}
		}
		.bottomBtn{
			width:750upx;
			height:80upx;
			text-align: center;
			line-height: 80upx;
			font-size:34upx;
			font-family:PingFang;
			font-weight:bold;
			position: fixed;
			bottom: 0;
			color:rgba(255,255,255,1);
			background:rgba(3,187,219,1);
		}
	}
</style>
