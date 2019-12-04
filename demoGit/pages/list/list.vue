<template>
<view class="container">
	<button type="primary" @tap="show('111')">1111</button>
	<view class="content" >
		<view class="topTab" 
		v-for="(item,index) in data" 
		:key="index"
		:class="{selected:currentIdex==index}"
		@click="tapClick(index,ref)"
		>
			{{item.name}}
		</view>
	</view>
	
	<Content  ref=content>
		<swiper :autoplay="true" :interval="3000" :duration="1000" 
		class="shopList"
		 >
			<swiper-item  
			v-for="(item,index) in dataImg"
			:key="index"
			class="swiper-item"
		 >
				<view class="title">{{item.title}}</view>
				<view class="author">{{item.author}}</view>
				<view class="img">
					<image :src="item.images"></image>
				</view>
			</swiper-item>
			
		</swiper>
		
				
	</Content>
	
		<QSPopup  ref='111' type='fadeInUp'>
			
			<view style="width: 500upx;height: 400upx;background: red;">oooo000</view>
		</QSPopup>


	<view style="width: 500upx;height: 400upx;background: red;" v-show="isshow">oooo000</view>	
	
</view>

	
</template>

<script>
	// import popupLayer from '../../components/popup-layer/popup-layer.vue';
	import QSPopup from '../../components/QS-popup/QS-popup.vue'
	import Content from '../../components/content/content.vue'
	import json from '@/json'
	export default {
		data() {
			return {
				boolShow:false,
				color:'#FF0060',
				isshow:0,
				data:[],
				currentIdex:0,
				dataImg:[],
				 animationData: {},	
			}
		},
		onLoad() {
			this.data =json.tabList
			this.dataImg =json.newsList
			var animation = uni.createAnimation({
			      duration: 1000,
			        timingFunction: 'ease',
			   })
		},
		components:{
			QSPopup,
			Content
		},
		methods: {
			
			show(ref) {
				this.$refs[ref].show();
				// console.log(this.$refs) 
			},
			tapClick(index,ref){
				this.currentIdex=index
				// console.log(this.$refs.content.$el)
				var tes1=this.$refs.content.$el
				
			},
			
		}
	}
</script>

<style lang="scss" scoped>
.content{
	width: 100%;
	height: 80upx;
	background: skyblue;
	display: flex;
	flex-direction: row;
	justify-content:space-around;
	align-items: center;

}
.topTab{
		height:100%;
		line-height: 80upx;
		background: #ccc;
		width: 60upx;
		margin-right: 10upx;
		font-size: 30upx;
	}
.selected{
		background: pink;
		color: #4CD964;
		border-bottom: 2upx solid #000;
	}
	.shopList{
		width: 100%;
		height: 1400upx;
	}
	.shopList .swiper-item{
		width: 100%;
		height: 100%;
	}
	.shopList .title{
		font-size: 40upx;
		font-weight: bold;
		color: #000;
	}
	.shopList .author{
		font-size: 15px;
		color: #ccc;
	}
	
	
</style>
