<template>
	<view class="container">
		<view class="shopMessage">
			<image src="../../static/shop_3.png"></image>
			<view class="navBar">
				<image src="../../static/nav bar.png" class="navBar"></image>
			</view>
		</view>
		<view class="des">
			<view class="desContent">
				<text class="buyContent">抢购:</text>
				<text class="buyPrice">￥50</text>
				<del class="delPrice">￥90元</del>
			</view>
			<view class="integral">
				<text class="jifen">积分</text>
				<text class="jifen1">积分低20%</text>
				<text class="jifen2">货返10积分</text>
			</view> 
			<view class="content">
				<text class="contentName">碧螺春云雾新绿茶罐装新茶</text>
				<text class="contentDes">中国传统名茶,中国十大名茶之一,属于绿茶类,已经有100多年历史。</text>
			</view>
			<view class="shopDetail">
				<view class="detail">商品详情</view>
					<view class="brand">
						<text class="brandBB">品牌</text>
						<text class="brandName">碧螺春</text>
					</view>
					<view class="place">
						<text class="Place">产地</text>
						<text class="PlaceName">苏州</text>
					</view>
					<view class="weight">
						<text class="Weight">净含量</text>
						<text class="WeightKg">259克</text>
					</view>
					<view class="way">
						<text class="Way">包装方式</text>
						<text class="Wayff">罐装</text>
					</view>
				</view>	
			</view>	
		<view class="button">
			<text class="zhankai">
				展开
			</text>
			<image src="../../static/middle_More.png"></image>
		</view>
		<view class="middleImage">
			<image src="../../static/shop_3.png"></image>
		</view>
		<view class="like">
			<view class="detail">大家还喜欢</view>
		</view>
		<view class="list">
			<view class="item">
				<image src="../../static/shop_3.png"></image>
				<view class="listDsc">
					<text class="listDscContent">碧螺春云雾新绿茶罐装新茶</text>
					<text class="listDscdes">中国传统名茶,中国十大名茶之一,属于绿茶类,已经有100多年历史。</text>
					<view class="foot">
						<text class="listPrice">￥50</text>
						<text class="listRec">热销推荐</text>
					</view>
				</view>
			</view>
			<view class="item">
				<image src="../../static/shop_3.png"></image>
				<view class="listDsc">
					<text class="listDscContent">碧螺春云雾新绿茶罐装新茶</text>
					<text class="listDscdes">中国传统名茶,中国十大名茶之一,属于绿茶类,已经有100多年历史。</text>
					<view class="foot">
						<text class="listPrice">￥50</text>
						<text class="listRec">热销推荐</text>
					</view>
				</view>
				
			</view>
			<view class="item">
				<image src="../../static/shop_3.png"></image>
				<view class="listDsc">
					<text class="listDscContent">碧螺春云雾新绿茶罐装新茶</text>
					<text class="listDscdes">中国传统名茶,中国十大名茶之一,属于绿茶类,已经有100多年历史。</text>
					<view class="foot">
						<text class="listPrice">￥50</text>
						<text class="listRec">热销推荐</text>
					</view>
				</view>
			</view>	
			<view class="item">
				<image src="../../static/shop_3.png"></image>
				<view class="listDsc">
					<text class="listDscContent">碧螺春云雾新绿茶罐装新茶</text>
					<text class="listDscdes">中国传统名茶,中国十大名茶之一,属于绿茶类,已经有100多年历史。</text>
					<view class="foot">
						<text class="listPrice">￥50</text>
						<text class="listRec">热销推荐</text>
					</view>
				</view>
			</view>
		</view>
		<view class="Footer"  @tap="show('QSPopup')" >
			立即购买
		</view>
		<QSPopup ref="QSPopup" type="fadeInUp" @goshop="goshop">
			<view class="popup" >
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
						<text   
							v-for="(item,index) in style"
							:key="index" 
							:class="{select:currentIndex==index,}"
							class="bc"
							@click="click(index)"
						 >
							{{item.name}}
							
						</text>
						<!-- <text class="hc">{{style[1].name}}</text>
						<text class="lc">{{style[1].name}}</text> -->
					</view>
					<view class="img">
						<text>数量</text>
						<image src="../../static/popup_Pickers.png"></image>
						<view class="ImgNum">1</view>
					</view>
				
				</view>
				<view class="footer"  @click="goshop">
					立即购买
				</view>
					
			</view>
		</QSPopup>
	</view>
		

		
</template>

<script>
	import QSPopup from '../../components/QS-popup/QS-popup.vue';
	import ypNumberBox from "@/components/yp-number-box/yp-number-box.vue";
	import popupLayer from '../../components/popup-layer/popup-layer.vue';
	export default {
		components:{
			QSPopup,
			ypNumberBox,
			popupLayer
		},
		data () {
			return {
				list:[
					{
						title: '碧螺春云雾新绿茶罐装明前新茶',
						conent: '中国传统茶艺，中国十大名茶之一，属于绿茶类，已有1000多年历史。',
						price: '50',
						integral: '积分',
						ptop: '20%'
					}
				],
				details: {
					shop: '商品详情',
					liked: '大家还喜欢'
				},
				//商品详情
				detailsList: [
					{
						name: '碧螺春',
						address: '江苏',
						ptre: '50kg',
						pftre: '罐装'
					}
				],
				//猜你喜欢
				likeList: [
					{
						url: '../../static/shop_pic02.png',
						title: '碧螺春云雾新绿茶罐装明前新茶',
						conent: '中国传统茶艺，中国十大名茶之一，属于绿茶类，已有1000多年历史。',
						price: '50',
						recom: '热销推荐'
					},
					{
						url: '../../static/shop_pic02.png',
						title: '碧螺春云雾新绿茶罐装明前新茶',
						conent: '中国传统茶艺，中国十大名茶之一，属于绿茶类，已有1000多年历史。',
						price: '50',
						recom: '热销推荐'
					},
					{
						url: '../../static/shop_pic02.png',
						title: '碧螺春云雾新绿茶罐装明前新茶',
						conent: '中国传统茶艺，中国十大名茶之一，属于绿茶类，已有1000多年历史。',
						price: '50',
						recom: '热销推荐'
					},
					{
						url: '../../static/shop_pic02.png',
						title: '碧螺春云雾新绿茶罐装明前新茶',
						conent: '中国传统茶艺，中国十大名茶之一，属于绿茶类，已有1000多年历史。',
						price: '50',
						recom: '热销推荐'
					}
				],
				specList: [
					{
						id: 1,
						name: '类型',
					},
				],
				specChildList: [
					{
						id: 1,
						pid: 2,
						name: '碧螺春',
					},
					{
						id: 2,
						pid: 2,
						name: '红茶',
					},
					{
						id: 3,
						pid: 2,
						name: '绿茶',
					},
				],
				style:[
					{
						id: 1,
						name: '碧螺春',
					},
					{
						id: 2,
						name: '红茶',
					},
					{
						id: 3,
						name: '绿茶',
					}
				],
				currentIndex:0
			}
		},
		onLoad() {
			//规格 默认选中第一条
				// this.specChildList.forEach(item=>{
					// for(let cItem of this.specChildList){
					// 	if(cItem.pid === item.id){
					// 		this.$set(cItem, 'selected', true);
					// 		this.specSelected.push(cItem);
					// 		// break; //forEach不能使用break
					// 	}
					// }
				// })
		},
		methods: {
				click(index){
					this.currentIndex=index
					
				},
				show(ref){
					this.$refs[ref].show()
				},
				goshop(){
					uni.navigateTo({
						url:"/pages/shop/order"
					})
				},
			  
			
			
			//选择规格
			selectSpec(index, pid){
				let list = this.specChildList;
				list.forEach(item=>{
					if(item.pid === pid){
						this.$set(item, 'selected', false);
					}
				})
				this.$set(list[index], 'selected', true);
				//存储已选择
				this.specSelected = []; 
				list.forEach(item=>{ 
					if(item.selected === true){ 
						this.specSelected.push(item); 
					} 
				})
				
			},
		},
	
		
		
		
		
		
	}


</script>

<style lang="scss" scoped>
	*{
		box-sizing: border-box;
	}
	.container {
		display: flex;
		flex-direction: column;
		justify-content: center;
		width: 750upx;
		min-height: 100upx;
		
	}
	.shopMessage{
		width: 750upx;
		height: 750upx;
		position: relative;
	}
	.shopMessage image{
		width: 100%;
		height: 100%;
		
	}
	.navBar image{
		position: absolute;
		top: 30upx;
		right: 4%;
		width: 200upx;
		height: 68upx;
	}
	.des{
		margin-top: 20upx;
		margin-left: 4%;
		visibility: middle;
	}
	.buyContent{
		font-size: 26upx;
		color: #FF0F6A;
		font-weight: bold;
		margin-right: 20upx;

	}
	.buyPrice{
		font-size:40upx;
		color: #FF0F6A;
		font-weight: bold;
		margin-right: 24upx;
	}
	.delPrice{
		font-size: 32upx;
		color: #BBBBBB;
	}
	.integral{
		margin-top: 7upx;
	}
	.jifen{
		width: 80upx;
		height: 42upx;
		background: #FF0060;
		color:#FF9DC1;
		font-size: 30upx;
		padding: 2upx 8upx;
		border-radius: 20upx;
		margin-right:20upx ;
	}
	.jifen1{
		width: 156upx;
		height: 42upx;
		background: #fff;
		border: 2upx solid #FF2E7D;
		border-radius: 20upx;
		color: #FF2E7D;
		font-size: 30upx;
		padding: 0 14upx;
		margin-right:20upx ;
	}
	.jifen2{
		width: 156upx;
		height: 42upx;
		background: #fff;
		border: 2upx solid #FF2E7D;
		border-radius: 20upx;
		color: #FF2E7D;
		font-size: 30upx;
		padding: 0 14upx;
	}
	.content{
		margin-top: 20upx;
	}
	.content .contentName{
		width: 392px;
		height: 40upx;
		font-size: 36upx;
		font-weight: bold;
		white-space: nowrap;
	}
.content .contentDes{
	display: block;
	width: 640upx;
	height: 56upx;
	margin-top: 10upx;
	font-size: 20upx;
	color: #A7A7A7;
}
.shopDetail{
	margin-top:40upx ;
	
}
.shopDetail .detail,.like .detail {
	border-left: 6upx solid #FF0060;
	width: 220upx;
	height: 50upx;
	line-height: 50upx;
	padding-left: 10upx;
	font-weight:bold;	
}
.brand{
	margin-top:30upx;
	border-top: 2upx solid #D1D1D1;
	padding: 10upx 10upx;
}
.brand .brandBB{
	width: 48upx;
	height: 34upx;
	font-size: 34upx;
	color: #D1D1D1;
	margin-right:160upx ;
}
.brand .brandName{
	width: 72upx;
	height: 34upx;
	font-size: 34upx;
	color: #626262;
	font-weight: bold;
}
.place{
	margin-top:14upx;
	border-top: 2upx solid #D1D1D1;
	padding: 10upx 10upx;
}
.place .Place{
	width: 48upx;
	height: 34upx;
	font-size: 34upx;
	color: #D1D1D1;
	margin-right:160upx ;
}
 .place .PlaceName{
	 width: 72upx;
	 height: 34upx;
	 font-size: 34upx;
	 color: #626262;
	 font-weight: bold;
 }
 .weight{
	margin-top:14upx;
	border-top: 2upx solid #D1D1D1;
	padding: 10upx 10upx;
 }
 .weight .Weight{
	width: 48upx;
	height: 34upx;
	font-size: 34upx;
	color: #D1D1D1;
	margin-right:124upx ;
 }
 .weight .WeightKg{
	width: 72upx;
	height: 34upx;
	font-size: 34upx;
	color: #626262;
	font-weight: bold;
 }
 .way{
	 margin-top:14upx;
	 border-top: 2upx solid #D1D1D1;
	 padding: 16upx 10upx;
	 border-bottom: 2upx solid #D1D1D1;
 }
 .way .Way{
	 width: 48upx;
	 height: 34upx;
	 font-size: 34upx;
	 color: #D1D1D1;
	 margin-right:88upx ;
 }
.way .Wayff{
	width: 72upx;
	height: 34upx;
	font-size: 34upx;
	color: #626262;
	font-weight: bold;
	
}
.button{
	margin-top: 12upx;
	margin-left:43% ;
	
}
.button text{
	font-size: 34upx;
	color:#BEBEBE;
	margin-right: 10upx;
}
.button image{
	width: 40upx;
	height: 40upx;
	vertical-align: middle;
}
.middleImage{
	margin-top: 44upx;
}
.middleImage image{
	width: 750upx;
	height: 750upx;
}
.like{
	margin-top: 40upx;
}
.list{
	margin-top: 20upx;
	margin-left:4%;
	margin-right: 4%;
	width:708upx ;
	display: flex;
	flex-wrap: wrap;
}
.list .item{
	margin-top: 30upx;
	width: 336upx;
	margin-right: 18upx;
}
.list .item image{
	width:336upx;
	height: 220upx;
}


.listDsc .listDscContent{
	width: 280px;
	height: 28upx;
	font-size: 28upx;
	font-weight: bold;
	
}
.listDsc .listDscdes{
	display: block;
	width: 316upx;
	height: 44upx;
	margin-top: 10upx;
	font-size: 20upx;
	color: #A7A7A7;
}
.foot{
	margin-top: 68upx;
}
.listPrice{
	font-size: 36upx;
	color: #FF5092;
	font-weight: bold;
}
.listRec{
	float: right;
	font-size: 26upx;
	color:#BBBBBB ;
	padding-top: 8upx;
}

.Footer{
	margin-top: 30upx;
	width: 100%;
	height: 98upx;
	background: #FF106A;
	text-align: center;
	line-height: 98upx;
	color: #fff;
	font-size: 40upx;
	
}

// 弹窗
.popup{
	width: 800upx;
	min-height: 100upx;
	background: #fff;

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
	// background: #D2D2D2;
}
.shopInfo .style text{
	width: 152upx;
	height: 42upx;
	// background: #D2D2D2;
	border-radius: 30upx;
	font-size: 30upx;
	padding: 4upx 40upx;
	margin-right: 40upx;
}

.shopInfo .select{
	background:#FF0060;
	color:#fff;
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
