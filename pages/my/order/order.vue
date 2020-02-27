<template>
	<view class="content">
		<view class="navBox">
			<view class="item" :class="{active:show==0}" @tap="changeShow(0)">
				全部
			</view>
			<view class="item" :class="{active:show==1}" @tap="changeShow(1)">
				待付款
			</view>
			<view class="item" :class="{active:show==2}" @tap="changeShow(2)">
				待发货
			</view>
			<view class="item" :class="{active:show==3}" @tap="changeShow(3)">
				待收货
			</view>
			<view class="item" :class="{active:show==4}" @tap="changeShow(4)">
				待评价
			</view>
		</view>
		<view class="order" v-if="show==0||show==1">
			<view class="top">
				<view class="orderNum">
					订单号：8208208820
				</view>
				<view class="status">
					待付款
				</view>
			</view>
			<view class="mid"  @tap="goDetails(1)">
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
			<view class="total">
				共1件商品  合计：<view class="totalPrice">￥399.00</view>
			</view>
			<view class="btnBox">
				<view class="item" @tap="cancel">
					取消订单
				</view>
			</view>
		</view>
		<view class="order" v-if="show==0||show==2">
			<view class="top">
				<view class="orderNum">
					订单号：8208208820
				</view>
				<view class="status">
					待发货
				</view>
			</view>
			<view class="mid" @tap="goDetails(2)">
				<image src="https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=1569869376,1108063482&fm=26&gp=0.jpg" mode=""></image>
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
			<view class="btnBox">
				<view class="item" @tap="remind">
					提醒发货
				</view>
				<!-- <view class="item">
					取消订单
				</view> -->
			</view>
		</view>
		<view class="order" v-if="show==0||show==3">
			<view class="top">
				<view class="orderNum">
					订单号：8208208820
				</view>
				<view class="status">
					待收货
				</view>
			</view>
			<view class="mid" @tap="goDetails(3)">
				<image src="https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=549042162,3015353700&fm=26&gp=0.jpg" mode=""></image>
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
			<view class="btnBox">
				<view class="item">
					查看物流
				</view>
				<view class="item" @tap="receivingGoods">
					确认收货
				</view>
			</view>
		</view>
		<view class="order" v-if="show==0||show==4">
			<view class="top">
				<view class="orderNum">
					订单号：8208208820
				</view>
				<view class="status">
					待评价
				</view>
			</view>
			<view class="mid" @tap="goDetails(4)">
				<image src="https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=1059674140,2466188286&fm=26&gp=0.jpg" mode=""></image>
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
			<view class="btnBox">
				<view class="item" @tap="goEvaluate">
					去评价
				</view>
			</view>
		</view>
		<view class="order" v-if="show==0">
			<view class="top">
				<view class="orderNum">
					订单号：8208208820
				</view>
				<view class="status">
					已完成
				</view>
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
			<view class="total">
				共1件商品  合计：<view class="totalPrice">￥399.00</view>
			</view>
			<view class="btnBox">
				<view class="item" @tap="deleteOrder">
					删除订单
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				show:0
			};
		},
		onLoad(e) {
			this.show=e.id
		},
		methods:{
			goDetails(type){
				uni.navigateTo({
					url: 'orderDetail/orderDetail?type='+type,
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			changeShow(id){
				this.show=id
			},
			goEvaluate(){
				uni.navigateTo({
					url: '../evaluate/evaluate',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			cancel(){
				uni.showModal({
				    title: '取消订单',
				    content: '确定要取消该订单吗',
				    success: function (res) {
				        if (res.confirm) {
				            console.log('用户点击确定');
				        } else if (res.cancel) {
				            console.log('用户点击取消');
				        }
				    }
				});
			},
			remind(){
				uni.showToast({
					title: '已提醒商家尽快发货',
					duration:2000
				});
			},
			receivingGoods(){
				uni.showModal({
				    title: '确认收货',
				    content: '确定收到货了吗？',
				    success: function (res) {
				        if (res.confirm) {
				            console.log('用户点击确定');
				        } else if (res.cancel) {
				            console.log('用户点击取消');
				        }
				    }
				});
			},
			deleteOrder(){
				uni.showModal({
				    title: '删除订单',
				    content: '确定要删除订单？',
				    success: function (res) {
				        if (res.confirm) {
				            console.log('用户点击确定');
				        } else if (res.cancel) {
				            console.log('用户点击取消');
				        }
				    }
				});
			}
		}
	}
</script>

<style lang="scss" scoped>
	.content{
		// position: absolute;
		// top: 0;
		// left: 0;
		// right: 0;
		// bottom: 0;
		height:auto!important;
		min-height:100vh;
		background: #F2F2F2;
		.navBox{
			display: flex;
			padding: 0 20upx;
			justify-content: space-between;
			height: 70upx;
			align-items: center;
			font-size:24upx;
			font-family:PingFang;
			font-weight:400;
			color:#BABABC;
			// opacity:0.3;
			background: #FFFFFF;
			.active{
				color: #333333;
			}
		}
		.order{
			background: #FFFFFF;
			width: 700upx;
			margin: 16upx auto 0;
			border-radius: 20upx;
			position: relative;
			padding-bottom: 146upx;
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
			.btnBox{
				display: flex;
				margin-top: 52upx;
				position: absolute;
				right: 24upx;
				// margin-left: 310upx;
				.item{
					margin-right: 20upx;
					text-align: center;
					line-height: 60upx;
					width:172upx;
					height:60upx;
					border:1upx solid rgba(214,214,214,1);
					border-radius:28upx;
					font-size:24upx;
					font-family:PingFang;
					font-weight:400;
					color:rgba(153,153,153,1);
				}
			}
		}
	}
</style>
