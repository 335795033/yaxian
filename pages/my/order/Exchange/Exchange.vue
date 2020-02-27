<template>
	<view class="content">
		<view class="order">
			<view class="top">
				<view class="orderNum">
					订单号：8208208820
				</view>
			</view>
			<view class="mid">
				<image src="../../../../static/goods%20(1).png" mode=""></image>
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
			<view class="total">
				共1件商品  合计：<view class="totalPrice">￥399.00</view>
			</view>
		</view>
		<view class="Choice">
			<view class="item">
				<view class="title">
					换货原因
				</view>
				<picker mode="selector" :range="arr" @change="changeN">
					<view v-if="n!=-1" style="color: #333333;" class="pick">{{arr[n]}}</view>
					<view class="pick" v-if="n==-1">请选择</view>
				</picker>
			</view>
			<view class="Explain">
				<view class="title">
					换货说明
				</view>
				<textarea value="" placeholder="请输入退款说明" />
			</view>
			<view class="uploadBox" @tap="uploadImg" v-if="phto==''">
				<image src="../../../../static/xiangj.png" mode=""></image>
				<view class="title">
					添加照片
				</view>
			</view>
			<view class="uploadBox" @tap="uploadImg"  v-if="phto!=''">
				<image :src="phto" mode=""></image>
			</view>
		</view>
		<view class="btnBox">
			提交
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				arr:['不喜欢','不好用','猫猫不喜欢'],
				n:-1,
				phto:''
			};
		},
		methods:{
			changeN(e){
				this.n=e.target.value
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
		height:auto!important;
		min-height:100vh;
		background: #F2F2F2;
		overflow: hidden;
		.order{
			background: #FFFFFF;
			width: 700upx;
			margin: 16upx auto 0;
			border-radius: 20upx;
			position: relative;
			padding-bottom: 34upx;
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
				.priceBox{
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
		.Choice{
			margin-top: 22upx;
			background: #FFFFFF;
			padding-bottom: 206upx;
			.item{
				display: flex;
				height: 80upx;
				justify-content: space-between;
				align-items: center;
				padding: 0 20upx;
				border-bottom: 2upx solid #F5F3F3;
				.title{
					font-size:28upx;
					font-family:PingFang;
					font-weight:bold;
					color:rgba(51,51,51,1);
				}
				.pick{
					font-size:26upx;
					font-family:PingFang;
					font-weight:400;
					color:rgba(153,153,153,1);
				}
				.nums{
					font-size:26upx;
					font-family:PingFang;
					font-weight:400;
					color:rgba(255,0,0,1);
				}
			}
			.Explain{
				.title{
					margin: 26upx 0 0 20upx;
					font-size:28upx;
					font-family:PingFang;
					font-weight:bold;
					color:rgba(51,51,51,1);
				}
				textarea{
					margin: 24upx auto 20upx;
					width:650upx;
					height:170upx;
					background:rgba(248,248,248,1);
					border-radius:10upx;
					padding: 20upx;
					font-size:24upx;
					font-family:PingFang;
					font-weight:400;
					color:rgba(51,51,51,1);
				}
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
		.btnBox{
			width:750upx;
			height:80upx;
			background:rgba(255,79,75,1);
			line-height: 80upx;
			text-align: center;
			font-size:36upx;
			font-family:PingFang;
			font-weight:bold;
			color:rgba(255,255,255,1);
			position: fixed;
			bottom: 0;
		}
	}
</style>
