<template>
	<view class="content">
		<view class="order-header">
			<view class="order-header-div">
				<p>星海<text>1235678987</text></p>
				<p>河南省郑州市梧桐街22号</p>
			</view>
			<image src="../../static/list_Top_Button.png"/>
		</view>
		<view class="order-main">
			<view class="shop-div">
				<image src="../../static/shop_3.png"></image>
				<view class="shop-div1">
					<h5>碧螺春云雾新绿茶罐装明前新茶</h5>
					<p>类型:碧螺春</p>
					<p>￥50</p>
					<p>积分抵20% <text>x1</text></p>
					
				</view>
			</view>
			<view class="shop-div2">
				<view class="Num">数量
					<text class="empty"></text>
					<text class="less">-</text>
					<text class="unm">1</text>
					<text class="add">+</text>
				</view>
				<view>配送</view>
				<view class="word">留言 <text>给商家留言(限50字)</text></view>
				<view>可用100积分抵扣￥10 
					<text 
					style="
					display: inline-block;
					margin-left: 200upx;
					
					width: 80upx;
					height: 30upx;
					"
					>  <switch checked  />
					</text>
				</view>
			</view>
		</view>
		<view class="Footer">
			<view class="pay">
				<text class="realyPay">实际付款:</text>
				<text class="realyPayPrice">￥40</text>
				<text class="realyPayTran">免运费</text>
				<text class="realyPayAccept">收货返10积分</text>
			</view>
			<view class="rushPay" @click="gopay">立即付款</view>
		</view>
	</view>
</template>

<script>
	export default {
		data () {
			return {
				
			}
		},
		methods: {
			gopay(){
				uni.redirectTo({
					url:"/pages/shop/address"
				})
				console.log('00000')
			}
		}
	}
</script>

<style lang="scss" scoped>
	*{
		box-sizing: border-box;
	}
	.content {
		width: 100%;
		background: #F5F5F5;
		min-height: 100upx;
		padding-left: 4%;
		padding-right: 4%;
	}
	.order-header {
		height: 180upx;
		padding: 20upx 20upx;
		border-radius: 30upx;
		overflow: hidden;
		display: flex;
		align-items: center;
		justify-content: space-between;
		background: url(../../static/list_Backgroud.png) no-repeat;
		background-size:cover;
		image {
			width: 30px;
			height: 30px;
		}
	}
	.order-header-div {
		p {
			font-size: 30upx;
			color: #3B3B3B;
		}
		p:nth-of-type(1) {
			margin-bottom: 15rpx;
			text {
				padding-left: 50rpx;
				
			}
		}
		p:nth-of-type(2){
			color: #989898;
		}
	}
	.order-main {
		width: 100%;
		height: 300px;
		border-radius: 15px;
		background: #fff;
		margin-top: 15px;
	}
	.shop-div {
		width: 93%;
		height: 265rpx;
		background: #fff;
		padding: 10rpx 22rpx;
		border-radius: 15px;
		margin-top: 10px;
		display: flex;
		
		image {
			width: 100px;
			height: 100px;
			margin-right: 20upx;
		}
	}
	.shop-div1 {
		margin-right: 30upx;
		h5 {
			font-size: 14px;
			color: #9D9D9D;
			margin-top: 5px;
		}
		p {
			font-size: 22upx;
			margin-top: 6upx;
			color: #7C7C7C;
		
		}
		p:nth-of-type(1) {
			color: #7C7C7C;
		}
		p:nth-of-type(2) {
			color: #FF0060;
			font-size: 17px;
		}
		p:nth-of-type(3) {
			color: #FF0060;
			margin-top: 10upx;
			
		}
		p:nth-of-type(3)>text{
			color: #000000;
			margin-left: 160upx;
			font-size: 24upx;
		}
		image {
			width: 50%;
			height: 50rpx;
			margin-top: 22rpx;
		}
	}
	.shop-div2 {
		view {
			width: 94%;
			height: 30px;
			line-height: 30px;
			padding: 0 22rpx;
			color: #626262;
			font-size: 30upx;
			border-top: 1px solid #E6E6E6;
		
		}
		
	}
.shop-div2 .Num .empty{
	margin-right: 60%;
}
.shop-div2 .Num .less,.add{
	display: inline-block;
	width:40upx;
	height: 40upx;
	line-height: 40upx;
	text-align: center;
	border-radius: 50%;
	background: #D2D2D2;
	font-size: 45upx;
	color: #A8A8A8;
	
	
}
.shop-div2 .Num .less{
	margin-right:30upx;
}
.shop-div2 .Num .unm{
	font-size: 38upx;
	margin-right:30upx;
}

.shop-div2 .word>text{
	font-size: 26upx;
	margin-left: 40upx;
	color: #E4E4E4;
}
.Footer{
	position: absolute;
	bottom: 0;
	width:100%;
	height: 112upx;
	background: #fff;
	display: flex;
	
}
 .Footer .pay{
	width:60%;
	height: 112upx;	
	background: #ffff;
	margin-left: 9.8%;
	
	 
 }
 
.Footer .pay .realyPay{
	font-size: 36upx;
	font-weight: bold;
	margin-right: 20upx;
}
.Footer .pay .realyPayPrice{
	font-size: 46upx;
	color: #FF106A;
	font-weight: bold;
	margin-right: 20upx;
}
.Footer .pay .realyPayTran{
	font-size: 26upx;
	color: #FF106A;
	font-weight: bold;
	
}
.Footer .pay .realyPayAccept{
	display: block;
	font-size:30upx;
	color: #FF106A;
}
.Footer .rushPay{
	width:40%;
	height: 112upx;
	line-height: 112upx;
	text-align: center;
	color: #fff;
	background:#FF106A ;
	overflow: hidden;
}
</style>
