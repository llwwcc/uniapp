<template>
	<view class="container">
		<view class="header">
			<view class="Receiver">
				<text class="receiver">收件人</text>
				<text class="receiverName">星海</text>
			</view>
			<view class="phone">
				<text class="phoneNum">手机号码</text>
				<text class="receiverPhone">12345678910</text>
			</view>
			<view class="address">
				<text class="receiverAddress">所在地区</text>
				<text class="receiverAddressPlace">河南 郑州市 高新区</text>
			</view>
			<view class="addressInfo">
				<text class="addressPlace">详细地址</text>
				<text class="addressInfoDes">梧桐街22号</text>
			</view>
		</view>
		<view class="footer">
			<view class="content">完成</view>
		</view>
	</view>
</template>

<script>
</script>

<style lang="scss" scoped>
	.container{
		width: 100%;
		min-height: 100upx;
		
	}
	.header{
		padding: 34upx 4%;
		background: #FFFFFF;
	}
	.Receiver{
		padding-bottom: 20upx;
		border-bottom: 2upx solid #C8C7CC;
	}
	.Receiver .receiver{
		font-size:36upx;
		color: #646464;
		margin-right: 17%;
	}
	.Receiver .receiverName{
		font-size:32upx;
		// color:#A5A5A5;
	}
	.phone{
		margin-top: 20upx;
		padding-bottom: 20upx;
		border-bottom: 2upx solid #C8C7CC;
	}
	.phone .phoneNum{
		font-size:36upx;
		color: #646464;
		margin-right: 12%;
	}
	.phone .receiverPhone{
		font-size:32upx;
		// color:#A5A5A5;
	}
	.address{
		margin-top: 20upx;
		padding-bottom: 20upx;
		border-bottom: 2upx solid #C8C7CC;
	}
	.address .receiverAddress{
		font-size:36upx;
		color: #646464;
		margin-right: 12%;
	}
	.address .receiverAddressPlace{
		font-size:32upx;
		// color:#A5A5A5;
	}
	.addressInfo{
		margin-top: 20upx;
		padding-bottom: 20upx;
		
	}
	.addressInfo .addressPlace{
		font-size:36upx;
		color: #646464;
		margin-right: 12%;
	}
	.addressInfo .addressInfoDes{
		font-size:32upx;
		// color:#A5A5A5;
	}
	.footer{
		margin-top: 7%;
		width: 100%;
		min-height: 1200upx;
		background: #F5F5F5;
		padding-top: 66upx;
		
	}
	.footer .content{
		width: 92%;
		margin-left: 4%;
		height: 98upx;
		background:#FF106A;
		border-radius: 45upx;
		color: #fff;
		text-align: center;
		line-height: 98upx;
	}
</style>
