<template>
	<view>
		<view class="content">
			<view class="list">
				<view class="row">
					<view class="title">头像</view>
					<view class="right"><view class="tis">
					<image src="/static/img/face.jpg" mode="widthFix"></image>
					</view><view class="icon xiangyou"></view></view>
				</view>
				<view class="row">
					<view class="title">昵称</view>
					<view class="right"><view class="tis">淘才宝</view><view class="icon xiangyou"></view></view>
				</view>
				<view class="row">
					<view class="title">个性签名</view>
					<view class="right"><view class="tis">淘才宝--专业的平台</view><view class="icon xiangyou"></view></view>
				</view>
				<view class="row">
					<view class="title">地址管理</view>
					<view class="right"><view class="tis"></view><view class="icon xiangyou"></view></view>
				</view>
				<view class="row">
					<view class="title">账户安全</view>
					<view class="right"><view class="tis"></view><view class="icon xiangyou"></view></view>
				</view>
			</view>
			<view class="list">
				<view class="row">
					<view class="title">通知提醒</view>
					<view class="right"><view class="tis"></view><view class="icon xiangyou"></view></view>
				</view>
<!-- 				<view class="row">
					<view class="title">支付设置</view>
					<view class="right"><view class="tis"></view><view class="icon xiangyou"></view></view>
				</view> -->
				<view class="row">
					<view class="title">通用</view>
					<view class="right"><view class="tis"></view><view class="icon xiangyou"></view></view>
				</view>
			</view>
			<view class="list">
				<view class="row">
					<view class="title">版本升级</view>
					<view class="right"><view class="tis">v1.0.0</view><view class="icon xiangyou"></view></view>
				</view>
				<view class="row">
					<view class="title">问题反馈</view>
					<view class="right"><view class="tis"></view><view class="icon xiangyou"></view></view>
				</view>
				<view class="row">
					<view class="title">关于淘才宝</view>
					<view class="right"><view class="tis"></view><view class="icon xiangyou"></view></view>
				</view>
			</view>
			<view class="list">
				<view class="row" @tap="logout">
					<view class="title">退出登录</view>
					<view class="right"><view class="tis"></view><view class="icon xiangyou"></view></view>
				</view>
			</view>
			
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		},
		methods: {
			showType(tbIndex){
				this.tabbarIndex = tbIndex;
				this.list = this.orderList[tbIndex];
			},
			// 退出
			logout(){
				uni.setStorageSync('token','');
				uni.reLaunch({
					url:'../../login/login',
				})
				
			}
		}
	}
</script>

<style lang="scss">
page{
	background-color: #f3f3f3;	
}

.icon {
	font-size: 30upx;

}
.content{
	padding-bottom: 20upx;
	.list{
		width: 96%;
		padding-left: 4%;
		background-color: #fff;
		margin-bottom: 20upx;
		.row{
			widows: 100%;
			min-height: 90upx;
			display: flex;
			align-items: center;
			justify-content: space-between;
			border-bottom: solid 1upx #eee;
			&:last-child{
				border-bottom: none;
			}
			.title{
				font-size: 32upx;
				color: #333;
			}
			.right{
				display: flex;
				align-items: center;
				color: #999;
				.tis{
					font-size: 26upx;
					margin-right: 5upx;
					max-height: 120upx;
					image{
						width: 100upx;
						height: 100upx;
						border-radius: 100%;
						margin: 10upx 0;
					}
				}
				.icon{
					width: 40upx;
					color: #cecece;
				}
			}
			
		}
	}
}

</style>
