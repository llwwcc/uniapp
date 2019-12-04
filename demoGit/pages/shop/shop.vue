<template>
	<view class="container">
		<view class="header">
			<view class="search">
				<view class="searchList">
					<view class="searchItem" id="searchContent">
					热搜:
					</view>
					<view class="searchItem " v-for="(item1,index) in list" :key="index" @click="tapClick(index)">
						{{item1}}
					</view>
				<!-- 	<view class="searchItem">
						速食
					</view>
					<view class="searchItem">
						饮品
					</view>
					<view class="searchItem">
						饮品
					</view> -->
				</view>
			</view>
			<view class="recommend">
				<view class="recommendList">
					<view class="recommendItem" id="recommendContent">
						推荐
					</view>
					<view class="recommendItem" 
					v-for="(item,index) in recommend " 
					:key="index" 
					 @click="tapClick(index)"
					
					>
					<!-- @tap="show('QSPopup')" -->
						{{item}}
					</view>
				<!-- 	<view class="recommendItem">
						日用品
					</view>
					<view class="recommendItem">
						保健品
					</view>
					<view class="recommendItem">
						保健品
					</view>	 -->
				<!-- 	<QSPopup ref=QSPopup type="fadeInLeft" class="QSPopup">
						<view class="yinpin" style="height: 50vh;width:100%;background-color: red; color: pink; z-index: 9999;" >
							饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品
							饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品饮品
						</view>
					</QSPopup> -->
					
					
				</view>
			</view>
		</view>	
		
		<!-- 轮播图	 -->
		<view class="swiper">
			<swiper class="swiperList" :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration" >
				<swiper-item>
					<image src="../../static/shop_3.png" ></image>
				</swiper-item>
				<swiper-item>
					2
				</swiper-item>
				<swiper-item>
					23
				</swiper-item>
			</swiper>
		</view>
		<!-- 商品 -->
		<view class="shop">
			<view class="shopList" style="margin-top: 20uxp;"
			 v-for="(item1,index1) in shopList" 
			 :key='index1'
			 v-if="isShow"
			>	
				<view class="shopImg">
					<image :src="item1.shopImg" ></image>
				</view>
				<view class="des">
					<text class="dscContent">{{item1.title}}</text>
					<text class="desDetail">{{item1.conent}}</text>
					<view class="buy">
						<text class="buyContent">抢购价:</text>
						<text class="buyPrice">{{item1.price}}</text>					
						<del  class="delPrice">{{item1.delPrice}}</del>
					</view>
					<view class="rush">
						<image src="../../static/list_Button.png" @click="buy"></image>
					</view>
				</view>		
			</view>
			
			<!-- <view class="shopList">
				<view class="shopImg">
					<image src="../../static/shop_3.png" ></image>
				</view>
				<view class="des">
					<text class="dscContent">碧螺春云雾新绿茶罐装新茶</text>
					<text class="desDetail">中国传统名茶,中国十大名茶之一,属于绿茶类,已经有100多年历史.</text>
					<view class="buy">
						<text class="buyContent">抢购价:</text>
						<text class="buyPrice">￥50</text>					
						<del  class="delPrice">￥90元</del>
					</view>
					<view class="rush">
						<image src="../../static/list_Button.png"></image>
					</view>
				</view>		
			</view> -->
			<!-- <view class="shopList">
				<view class="shopImg">
					<image src="../../static/shop_3.png" ></image>
				</view>
				<view class="des">
					<text class="dscContent">碧螺春云雾新绿茶罐装新茶</text>
					<text class="desDetail">中国传统名茶,中国十大名茶之一,属于绿茶类,已经有100多年历史.</text>
					<view class="buy">
						<text class="buyContent">抢购价:</text>
						<text class="buyPrice">￥50</text>					
						<del  class="delPrice">￥90元</del>
					</view>
					<view class="rush">
						<image src="../../static/list_Button.png"></image>
					</view>
				</view>		
			</view> -->
		</view>
		
		
		
		
		
	</view>
	
	
</template>

<script>
	// import QSPopup from '../../components/QS-popup/QS-popup.vue';
	export default {
		// components:{QSPopup},
		data () {
			return {
			
				list: [
					'茶叶',
					'速食',
					'饮品',
					'饮品'
				],
				recommend: [
					'饮品',
					'日用品',
					'保健品',
					'保健品'
				],
				recommendIndex:0,
				isShow:false,
				//轮播图
				background: ['color1', 'color2', 'color3'],
				indicatorDots: true,
				autoplay: true,
				interval: 2000,
				duration: 500,
				//商品列表
				shopList: [
					{
						shopImg:'../../static/shop_3.png',
						title: '碧螺春云雾新绿茶罐装明前新茶',
						conent: '中国传统茶艺，中国十大名茶之一，属于绿茶类，已有1000多年历史。',
						price: '￥50',
						delPrice:'￥90元',
						url: '../../static/list_Button.png'
					},
					{	shopImg:'../../static/shop_3.png',
						title: '碧螺春云雾新绿茶罐装明前新茶',
						conent: '中国传统茶艺，中国十大名茶之一，属于绿茶类，已有1000多年历史。',
						price: '50',
						delPrice:'￥90元',
						url: '../../static/list_Button.png'
					},
					{	
						shopImg:'../../static/shop_3.png',
						title: '碧螺春云雾新绿茶罐装明前新茶',
						conent: '中国传统茶艺，中国十大名茶之一，属于绿茶类，已有1000多年历史。',
						price: '50',
						delPrice:'￥90元',
						url: '../../static/list_Button.png'
					}
				]
			}
		},
		onLoad: {
			// this.getShop()
		},
		methods: {
			// 头部轮播
			// changeIndicatorDots(e) {
			//     this.indicatorDots = !this.indicatorDots
			// },
			// changeAutoplay(e) {
			//     this.autoplay = !this.autoplay
			// },
			// intervalChange(e) {
			//     this.interval = e.target.value
			// },
			// durationChange(e) {
			//     this.duration = e.target.value
			// },
			//获取商品数据
			buy(){
				uni.navigateTo({
					url:"/pages/shop/shop-details"
				})
			},
			tapClick(index){
				if(index == 0){
					this.isShow=true
				}else{
					this.isShow=false
				}
				
			}
		}
	}
</script>

<style lang="scss" scoped>
	//头部
	*{
		box-sizing: border-box;
	}
	.container{
		width: 100%;
		min-height: 100upx;
		
		
	}
	.header{
		width: 100%;
		height: 300upx;
		background:#FF0060 ;
		padding-left: 30upx;
		padding-top: 6upx;
		position: relative;
	}
	.search{
		height: 80upx;
		color:#FFAACA ;
		margin-right: 20upx;
		// margin-bottom: 20upx;
	}
	#searchContent{
		font-size: 32upx;
		
		border: none;
	}
	.searchList{
		margin-top: 10upx;
		height: 80upx;
		display: flex;
	}
	.searchItem{
		width: 106upx;
		height: 22px;
		font-size: 34upx;
		border: 2upx solid #FF7DAD;
		margin-right: 24upx;
		text-align: center;
		border-radius: 30upx;
		
	}
	.recommendList{
		display: flex;
		
	}
	#recommendContent{
		width: 112upx;
		height: 48upx;
		text-align: center;
		line-height: 48upx;
		background: #FF80AF;
		border-radius: 30upx;
		font-size: 34upx;
		color:#FFF2F6;
		margin-right: 8%;
	}
	.recommendItem{
		width: 120upx;
		height: 40upx;
		color: #FFFBFC;
		font-size:32upx;
		font-weight: bold;
		margin-right: 3%;
	}
	
	// 轮播图
	.swiper{
		position: absolute;
		top: 164upx;
		left: 4%;
		width:92%;
		height: 246upx;
	
	}
	.swiperList{
		width: 100%;
		height: 100%;
		border-radius: 30upx;
		border: 2upx solid #000;
		
	}
	.swiperList image{
		width: 100%;
		height: 100%;
		border-radius: 30upx;
		// overflow: hidden;
	}
	.shop{
		width: 100%;
		height: 800upx;
		background:#F5F5F5;
		padding-top: 156upx;
		padding-left: 24upx;
	}
	.shopList{
		width: 706upx;
		height: 276upx;
		background-color: #FFFFFF;
		border-radius: 30upx;
		display: flex;
		margin-top: 20upx;
	}
	.shopImg{
		width:220upx;
		height: 220upx;
		margin-right: 20upx;
		
		
	}
	.shopImg image{
		width: 100%;
		height: 100%;
		border-radius: 30upx;
	}
	.des{
		flex: 1;
		// width: 196px;
		// height: 40upx;
		
		
	}
	.dscContent{
		width: 392px;
		height: 40upx;
		font-size: 30upx;
		font-weight: bold;
		white-space: nowrap;
	}
	.desDetail{
		display: block;
		width: 410upx;
		height: 56upx;
		margin-top: 10upx;
		font-size: 20upx;
		color: #A7A7A7;
	}
	.buy{
		margin-top: 20upx;
	}
	.buyContent{
		font-size: 24upx;
		color: #FF0F6A;
		margin-right: 20upx;
		font-weight: bold;
	}
	.buyPrice{
		font-size: 30upx;
		color: #FF0F6A;
		font-weight: bold;
		margin-right: 24upx;
	}
	.delPrice{
		font-size: 34upx;
		color: #BBBBBB;
		text-decoration: line-through;
	}
	.rush{
		width: 176upx;
		height: 42upx;
		margin-top: 8upx;
	}
	.rush image{
		width: 100%;
		height: 100%;
	}
	.QSPopup{
		z-index: 999;
	}
</style>
