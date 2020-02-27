<template>
	<view class="content">
		<view class="container">
			<image src="../../../static/rz.png" mode=""></image>
			<view class="inputS">
				<view class="item">
					<view class="title">
						真实姓名
					</view>
					<input type="text" value="" placeholder="请输入真实姓名"/>
				</view>
				<view class="item">
					<view class="title">
						身份证号
					</view>
					<input type="text" value="" placeholder="请输入15位或18位身份证号"/>
				</view>
			</view>
			<view class="upload">
				<view class="title">
					上传身份证照片
				</view>
				<view class="uploadBox" @tap="uploadImg(0)" v-if="Positive==''">
					<image src="../../../static/xiangji.png" mode=""></image>
					<view class="name">
						正面照片
					</view>
				</view>
				<image class="photo" @tap="uploadImg(0)" :src="Positive" mode="" v-if="Positive!=''"></image>
				<view class="uploadBox"  @tap="uploadImg(1)" v-if="back==''">
					<image src="../../../static/xiangji.png" mode=""></image>
					<view class="name">
						反面照片
					</view>
				</view>
				<image class="photo" @tap="uploadImg(1)" :src="back" mode="" v-if="back!=''"></image>
				<view class="btn">
					立即认证
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				Positive:'',//正面照
				back:''//反面照
			};
		},
		methods:{
			uploadImg(id){
				uni.chooseImage({
				    success: (chooseImageRes) => {
				        const tempFilePaths = chooseImageRes.tempFilePaths;
						// console.log(tempFilePaths[0])
						if(id==0){
							this.Positive=tempFilePaths[0]							
						}else if(id==1){
							this.back=tempFilePaths[0]
						}
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
		.container{
			image{
				width: 100%;
				height: 200upx;
			}
			.inputS{
				position: relative;
				margin-top: -20upx;
				background:rgba(255,255,255,1);
				border-radius:16upx 16upx 0px 0px;
				padding: 0 45upx;
				.item{
					display: flex;
					height: 98upx;
					border-bottom: 2upx solid #F1F1F1;
					align-items: center;
					.title{
						font-size:30upx;
						font-family:PingFang;
						font-weight:500;
						color:rgba(51,51,51,1);
					}
					input{
						margin-left: 40upx;
						font-size:28upx;
						font-family:PingFang;
						font-weight:500;
						color:rgba(179,179,179,1);
						width: 70%;
					}
				}
			}
			.upload{
				background: #FFFFFF;
				margin-top: 20upx;
				overflow: hidden;
				width: 100%;
				.title{
					font-size:30upx;
					margin: 30upx 0 0 30upx;
					font-family:PingFang;
					font-weight:500;
					color:rgba(51,51,51,1);
				}
				.uploadBox{
					width: 600upx;
					height: 338upx;
					margin: 30upx auto;
					border:2upx solid rgba(204,204,204,1);
					display: flex;
					flex-direction: column;
					justify-content: center;
					align-items: center;
					image{
						width: 86upx;
						height: 69upx;
					}
					.name{
						margin-top: 30upx;
						font-size:30upx;
						font-family:PingFang;
						font-weight:500;
						color:rgba(153,153,153,1);
					}
				}
				.photo{
					width: 600upx;
					height: 338upx;
					margin: 30upx auto;
					display: flex;
					justify-content: center;
				}
				.btn{
					width:600upx;
					height:88upx;
					background:rgba(3,187,219,1);
					border-radius:44upx;
					text-align: center;
					line-height: 88upx;
					margin: 50upx auto 0;
					font-size:36upx;
					font-family:PingFang;
					font-weight:bold;
					color:rgba(255,255,255,1);
				}
			}
		}
	}
</style>
