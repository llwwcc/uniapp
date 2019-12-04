<template>
	<view class="container">
		<view class="img">
			<image src="../../static/tanchuang.png" ></image>
		</view>
		<view class="Mess">
			<view class="message">
				<view class="smallImg">
					<image src="../../static/shop_3.png" ></image>
				</view>
				<view class="information">
					<view class="dec">碧螺春云雾新绿茶罐装明前新茶</view>
					<view class="price">￥50</view>
					<view class="inventory">库存456件</view> 	
				</view>
			</view>
		</view>
		<view class="shopInfo">
			<view class="num">类型</view>
			<view class="style">
				<text class="bl">碧螺春</text>
				<text class="hc">红茶</text>
				<text class="lc">绿茶</text>
			</view>
			<view class="img">
				<text>数量</text>
				<image src="../../static/popup_Pickers.png"></image>
				<view class="ImgNum">1</view>
			</view>
		
		</view>
		<view class="footer" @click="goShopping">
			立即购买
		</view>
	
		
		
		
	</view>
</template>

<script>
	export default{
		data(){
			return{
				
			}
		},
		methods:{
			goShopping(){
				uni.navigateTo({
					url:"/pages/shop/order"
				})
			}
		}
	}
</script>

<style lang="scss">
.container{
	width: 100%;
	min-height: 100upx;
	// height: 6000upx;

}
.img image{
	width:100%;
	height: 2978upx;
}
.message{
	position: relative;
	margin-left: 4%;
}
.smallImg{
	position: absolute;
	top: -58upx;
	left: -46upx;
	width: 260upx;
	height: 260upx;
	background: #fff;
	text-align: center;
}
.smallImg image{
	width: 240upx;
	height: 240upx;

}
.information{
	position: absolute;
	top: 10upx;
	left: 35%;
	
}
.information .dec{
	font-size: 30upx;
	font-weight: bold;
}
.information .price{
	margin-top: 20upx;
	font-size: 48upx;
	font-weight: bold;
	color: #FF0463;
}
.information .inventory{
	margin-top: 22upx;
	font-size: 30upx;
	color:#8C8C8C;
}
.Mess{
	margin-left: 4%;
	margin-right: 4%;
	height: 220upx;
	border-bottom: 2upx solid #D2D2D2;
}

.shopInfo{
	margin-top:18upx ;
	margin-left: 4%;
}
.num{
	font-size:40upx ;
	color: #B8B8B8;
}
.shopInfo .style{
	margin-top: 10upx;
}
.shopInfo .bl{
	width: 152upx;
	height: 42upx;
	background: #FF0060;
	border-radius: 30upx;
	font-size: 30upx;
	padding: 4upx 40upx;
	color: #fff;
	margin-right: 40upx;
}
.shopInfo .hc,.lc{
	width: 128upx;
	height: 42upx;
	background: #D2D2D2;
	font-size: 30upx;
	padding: 4upx 40upx;
	color:#535353;
	border-radius: 30upx;
	margin-right: 40upx;
}
.shopInfo .img	{
	margin-top: 20upx;
	position: relative;
}
.shopInfo .img text{
	font-size:40upx ;
	color: #B8B8B8;
	margin-right:53.3% ;
}	
.shopInfo .img image{
	width: 234upx;
	height: 56upx;
	vertical-align: middle;
	
}	
.shopInfo .img .ImgNum{
	position: absolute;
	top:4upx;
	right: 130upx;
}	
.footer{
	margin-top: 40upx;
	width: 100%;
	height: 98upx;
	background:#FF106A;
	color: #fff;
	font-size: 40upx;
	text-align: center;
	line-height:98upx;
}
</style>
