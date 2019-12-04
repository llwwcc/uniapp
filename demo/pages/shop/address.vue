<template>
	<view class="container">
		<view class="header">
			<view class="address1" v-for="(item,index) in list " :key="index">
				<view class="addressInfo">
					<text class="companyName">{{item.companyName}}</text>
					<text class="companyTellphone">{{item.companyTellphone}}</text>
					<text class="companyAddress">{{item.companyAddress}}</text>
				</view>
				<view class="option">	
					<text class="select"><image :src=item.ImgUrl ></image></text>
					<text class="selectAddress" @click="click(index)" >{{item.selectAddress}}</text>
					<text class="selectEditor"><image src="../../static/list_Button_Edit.png"></image>{{item.selectEditor}}</text>
					<text class="selectDel" @click="del(index)"><image src="../../static/list_Button_Delete.png"></image>{{item.selectDel}}</text>
				</view>
			</view>
			
			<!-- <view class="address2">
				<view class="addressInfo">
					<text class="companyName">星海</text>
					<text class="companyTellphone">12345678910</text>
					<text class="companyAddress">河南-郑州-高新区-梧桐街22号</text>
				</view>
				<view class="option">
					<text class="select"><image src="../../static/list_qunquan.png" ></image></text>
					<text class="selectAddress">设为默认</text>
					<text class="selectEditor"><image src="../../static/list_Button_Edit.png"></image>编辑</text>
					<text class="selectDel"><image src="../../static/list_Button_Delete.png"></image>删除</text>
				</view>
			</view> -->
			<!-- <view class="address3">
				<view class="addressInfo">
					<text class="companyName">星海</text>
					<text class="companyTellphone">12345678910</text>
					<text class="companyAddress">河南-郑州-高新区-梧桐街22号</text>
				</view>
				<view class="option">
					<text class="select"><image src="../../static/list_qunquan.png" ></image></text>
					<text class="selectAddress">设为默认</text>
					<text class="selectEditor"><image src="../../static/list_Button_Edit.png"></image>编辑</text>
					<text class="selectDel"><image src="../../static/list_Button_Delete.png"></image>删除</text>
				</view>
			</view> -->
		
		</view>
		<view class="footer" @click="addAddress">
			添加地址
		</view>
	</view>
	
</template>

<script>
	export default {
		data(){
			return{
				list:[
					{	
						id:1,
						companyName:"星海",
						companyTellphone:'111111111111',
						companyAddress:"河南-郑州-高新区-梧桐街22号",
						ImgUrl:'../../static/list_qunquan.png',						
						selectAddress:'设为默认',
						selectEditor:"编辑",
						selectDel:'删除'
					},
					{	id:2,
						companyName:"星海",
						companyTellphone:'22222222222',
						companyAddress:"河南-郑州-高新区-梧桐街22号",
						ImgUrl:'../../static/list_qunquan.png',
						selectAddress:'设为默认',
						selectEditor:"编辑",
						selectDel:'删除'
					},
					{
						id:3,
						companyName:"星海",
						companyTellphone:'333333333333',
						companyAddress:"河南-郑州-高新区-梧桐街22号",
						ImgUrl:'../../static/list_qunquan.png',
						selectAddress:'设为默认',
						selectEditor:"编辑",
						selectDel:'删除'
					}
				],
				path1:"../../static/list_Button_Selected.png",
				path2:"../../static/list_qunquan.png",
				isTure:true,
				isSelected:true,
			}
		},
		methods:{
			addAddress(){
				uni.redirectTo({
					url:"/pages/shop/shop_addAddress"
				})
			},
			click(index){
				console.log(index)
						if(this.isTure){
							this.list[index].ImgUrl=this.path1
							this.isTure=false;
							console.log(11111,this.isTure)
						}else{
							console.log(222)
							this.list[index].ImgUrl=this.path2
							this.isTure=true;
							
						}
				//
			
				
				
			},
			del(index){
				this.list.splice(index,1)
				
			}
		}
	}
</script>

<style lang="scss" scoped>
	*{
		box-sizing: border-box;
	}
	.container{
		min-height:100upx;
	}
	.header{
		width: 100%;
		// height: 1200upx;
		padding: 32upx 4%;
		background:#F5F5F5;
	}
	.address1{
		width:100%;
		height: 252upx;
		background: #ffff;
		border-radius: 30upx;
	
	}
	.address1 .companyName{
		margin-top: 24upx;
		font-size: 36upx;
		font-weight: bold;
		margin-right:8% ;
	}
	
	.address2 .companyName{
		margin-top: 24upx;
		font-size: 36upx;
		font-weight: bold;
		margin-right:8% ;
	}
	
	.address1 .companyTellphone{
		font-size: 36upx;
		font-weight: bold;
		
	}
	.address2 .companyTellphone{
		font-size: 36upx;
		font-weight: bold;
		
	}
	.address3 .companyTellphone{
		font-size: 36upx;
		font-weight: bold;
		
	}
	.address1 .companyAddress{
		display: block;
		font-size: 36upx;
		font-weight: bold;
		margin-top:20upx;
		
	}
	.address2 .companyAddress{
		display: block;
		font-size: 36upx;
		font-weight: bold;
		margin-top:20upx;
		
	}
	.address3 .companyAddress{
		display: block;
		font-size: 36upx;
		font-weight: bold;
		margin-top:20upx;
		
	}
	
	.addressInfo{
		padding:  24upx 28upx ;
		border-bottom: 2upx solid #E9E9E9;
		color: #555555;
	}
	.option{
		padding-left: 24upx;
		margin-top: 18upx;
		height: 34upx;
		line-height: 34upx;
	}
	.option	.select image{
		width: 50upx;
		height: 50upx;
		vertical-align: middle;
		margin-right: 20upx;
		
	}
	.option .selectAddress{
		font-size: 34upx;
		color:  #FF0060;
		margin-right:23%;
	}
	.option .selectEditor image{
		width: 50upx;
		height: 50upx;
		vertical-align: middle;
		
	}
	.option .selectDel image{
		width: 50upx;
		height: 50upx;
		vertical-align: middle;
	}
	.option .selectEditor{
		margin-right: 36upx;
	}
	.option .selectEditor,.option .selectDel{
		font-size: 34upx;
		color: #6E6E6E;
	}
	.address2{
		margin-top: 40upx;
		width:100%;
		height: 252upx;
		background: #ffff;
		border-radius: 30upx;
	}
	.address3{
		margin-top: 40upx;
		width:100%;
		height: 252upx;
		background: #ffff;
		border-radius: 30upx;
	}
	.footer{
		position: absolute;
		bottom: 0;
		width: 100%;
		height: 98upx;
		text-align: center;
		line-height: 98upx;
		background: #FF106A;
		color: #fff;
	}
</style>
