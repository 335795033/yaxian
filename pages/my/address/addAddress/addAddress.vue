<template>
	<view class="content">
		<view class="container">
			<view class="item">
				<view class="title">
					收货人:
				</view>
				<input type="text" value="" placeholder="请输入收货人姓名" />
			</view>
			<view class="item">
				<view class="title">
					收货人电话:
				</view>
				<input type="text" value="" placeholder="请输入收货人电话" />
			</view>
			<view class="item">
				<view class="title">
					所在地区:
				</view>
				<pickerAddress class="picker" @change="change">{{txt}}</pickerAddress>
			</view>
			<view class="adsDetail">
				<view class="title">
					详细地址:
				</view>
				<textarea value="" placeholder="请输入如：道路、门牌号、小区、楼栋号、单元等" />
				</view>
			<view class="bottom">
				<view class="title">
					默认地址
				</view>
				<switch color="#FD5555" style="transform:scale(0.7)" @change="switch2Change" />
			</view>
			<view class="bottomBtn">
				保存
			</view>
		</view>
	</view>
</template>

<script>
	import pickerAddress from '../../../../components/wangding-pickerAddress/wangding-pickerAddress.vue'
	export default {
		components: {
			pickerAddress
		},
		data() {
			return {
				txt: '请选择',
				title: 'Hello'
			};
		},
		methods: {
			change(data) {
				this.txt = data.data.join('')
				console.log(data.data.join(''))
			},
			 switch2Change: function (e) {
				console.log('switch2 发生 change 事件，携带值为', e.target.value)
			}
		}
	}
</script>

<style lang="scss" scoped>
	.content{
		position: absolute;
		left: 0;
		top: 0;
		right: 0;
		bottom: 0;
		background: #F7F7F5;
		.container{
			background: #FFFFFF;
			margin-top: 20upx;
			.item{
				display: flex;
				height: 80upx;
				align-items: center;
				border-bottom: 2upx solid #F7F7F5;
				.title{
					text-align-last: justify;
					width: 160upx;
					font-size:30upx;
					font-family:PingFang;
					font-weight:bold;
					color:rgba(51,51,51,1);
					margin-left: 20upx;
				}
				input{
					font-size:30upx;
					font-family:PingFang;
					color:rgba(51,51,51,1);
					margin-left: 10upx;
				}
				.picker{
					font-size:30upx;
					margin-left: 10upx;
					width: 400upx;
				}
			}
			.adsDetail{
				.title{
					text-align-last: justify;
					margin-top: 26upx;
					width: 160upx;
					font-size:30upx;
					font-family:PingFang;
					font-weight:bold;
					color:rgba(51,51,51,1);
					margin-left: 20upx;
				}
				textarea{
					margin: 20upx 0 0 20upx;
					font-size:30upx;
					width: 710upx;
					height: 200upx;
				}
			}
			.bottom{
				display: flex;
				border-top: 2upx solid #F7F7F5;
				height: 80upx;
				align-items: center;
				justify-content: space-between;
				.title{
					text-align-last: justify;
					width: 160upx;
					font-size:30upx;
					font-family:PingFang;
					font-weight:bold;
					color:rgba(51,51,51,1);
					margin-left: 20upx;
				}
			}
			.bottomBtn{
				position: fixed;
				bottom: 0;
				width:750upx;
				height:98upx;
				text-align: center;
				line-height: 98upx;
				font-size:34upx;
				font-family:PingFang;
				font-weight:bold;
				color:rgba(255,255,255,1);
				background:rgba(255,83,83,1);
			}
		}
	}
</style>
