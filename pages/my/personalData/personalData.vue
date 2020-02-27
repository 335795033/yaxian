<template>
	<view class="content">
		<view class="container">
			<view class="item">
				<view class="title">
					头像
				</view>
				<image src="https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=4227069332,3272640719&fm=11&gp=0.jpg" mode=""></image>
			</view>
			<view class="item">
				<view class="title">
					昵称
				</view>
				<input type="text" v-model="name" placeholder="请输入昵称" />
			</view>
			<view class="item">
				<view class="title">
					年龄
				</view>
				<input type="text" v-model="age" placeholder="请输入年龄" />
			</view>
			<view class="item">
				<view class="title">
					生日
				</view>
				<picker mode="date" :value="date" :start="startDate" :end="endDate" @change="bindDateChange">
					<view class="uni-input">{{date}}</view>
				</picker>
			</view>
			<view class="item">
				<view class="title">
					年龄
				</view>
				<picker mode="selector" :range="gender" @change="changeGender">
					<view v-if="n!=-1" class="uni-input">{{gender[n]}}</view>
					<view v-if="n==-1" class="uni-input">请选择</view>
				</picker>
			</view>
			<view class="item">
				<view class="title">
					学校
				</view>
				<input type="text" v-model="School" placeholder="请输入学校" />
			</view>
			<view class="item">
				<view class="title">
					邮箱
				</view>
				<input type="text" v-model="email" placeholder="请输入邮箱" />
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			const currentDate = this.getDate({
				format: true
			})
			return {
				name: "工藤新一",
				age: '18',
				date: '1996-06-18',
				gender:['男','女'],
				n:0,
				School:'',
				email:''
			};
		},
		computed: {
			startDate() {
				return this.getDate('start');
			},
			endDate() {
				return this.getDate('end');
			}
		},
		methods: {
			changeGender(e){
				this.n=e.target.value
			},
			bindDateChange: function(e) {
				this.date = e.target.value
			},
			getDate(type) {
				const date = new Date();
				let year = date.getFullYear();
				let month = date.getMonth() + 1;
				let day = date.getDate();

				if (type === 'start') {
					year = year - 60;
				} else if (type === 'end') {
					year = year + 2;
				}
				month = month > 9 ? month : '0' + month;;
				day = day > 9 ? day : '0' + day;
				return `${year}-${month}-${day}`;
			}
		}
	}
</script>

<style lang="scss" scoped>
	.content {
		position: absolute;
		left: 0;
		top: 0;
		right: 0;
		bottom: 0;
		background: #F1F1F1;

		.container {
			margin-top: 20upx;

			.item {
				display: flex;
				align-items: center;
				justify-content: space-between;
				background: #FFFFFF;
				height: 80upx;
				border-bottom: 2upx solid #F3F3F5;

				.title {
					margin-left: 20upx;
					font-size: 26upx;
					font-family: PingFang;
					font-weight: 400;
					color: rgba(51, 51, 51, 1);
					line-height: 26upx;
				}

				image {
					margin-right: 20upx;
					width: 50upx;
					height: 50upx;
					border-radius: 50%;
				}

				input {
					margin-right: 20upx;
					text-align: right;
					font-size: 26upx;
					font-family: PingFang;
					font-weight: 400;
					color: rgba(51, 51, 51, 1);
				}
				.uni-input{
					margin-right: 20upx;
					font-size:26upx;
					font-family:PingFang;
					font-weight:400;
					color:#333333;
				}
			}
		}
	}
</style>
