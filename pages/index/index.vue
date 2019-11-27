<template>
	<div>
		
		<div class="flexRowBetween seachbox fs13">
			<div class="flex white" @click="Router.navigateTo({route:{path:'/pages/index_jobEdit/index_jobEdit'}})">
				<img class="Licon mgr5" src="../../static/images/home-icon.png" >
				<span>会计</span>
				<img class="arrowR" src="../../static/images/home-icon1.png" >
			</div>
			<div class="flexRowBetween rr">
				<div class="input">
					<input type="" name="" id="" value="" placeholder="搜职位" />
				</div>
				<button class="seachBtn" type="button"></button>
			</div>
		</div>
		
		<div class="positionList pdlr4">
			<ul>
				<li v-for="item in positionDate">
					<div class="flexRowBetween pdtb15"  @click="Router.navigateTo({route:{path:'/pages/positionDetail/positionDetail'}})">
						<div class="flex ll">
							<img class="Lphoto" src="../../static/images/home-img.png" >
							<div class="infor">
								<p class="name fs14">会计助理</p>
								<p class="lable fs13">克莱</p>
								<p class="color9 fs12">西安&nbsp;|&nbsp;3年&nbsp;|&nbsp;本科</p>
							</div>
						</div>
						<div class="rr">
							<div class="red mgb20 flexEnd">4K-6K</div>
							<p class="fs12 color9 flexEnd">10月20日</p>
						</div>
					</div>
					<div class="flexRowBetween pdb15 adrss mglr4">
						<p class="flex adrssTit fs13 color6"><img class="adrsIcon mgr5" src="../../static/images/position-icon1.png"/>西安市雁塔区中投国际A座1802室</p>
						<div class="adrssIcon flexEnd">
							<img class="GpsIcon mgr15" src="../../static/images/workbench-icon2.png" >
						</div>
					</div>
				</li>
			</ul>
		</div>
		
		
		<!--底部tab键-->
		<div class="navbar flexRowBetween">
			<div class="navbar_item flexColumn" @click="Router.navigateTo({route:{path:'/pages/workbench/workbench'}})">
				<div class="nav_img">
					<img src="../../static/images/nabar1.png" />
				</div>
				<div class="text">工作台</div>
			</div>
			<div class="navbar_item" @click="Router.navigateTo({route:{path:'/pages/index/index'}})">
				<div class="nav_img">
					<img src="../../static/images/nabar2-a.png" />
				</div>
				<div class="text this-text">职位</div>
			</div>
			<div class="navbar_item" @click="Router.navigateTo({route:{path:'/pages/tidings/tidings'}})">
				<div class="nav_img">
					<img src="../../static/images/nabar3.png" />
				</div>
				<div class="text">消息</div>
			</div>
			<div class="navbar_item" @click="Router.navigateTo({route:{path:'/pages/user/user'}})">
				<div class="nav_img">
					<img src="../../static/images/nabar4.png" />
				</div>
				<div class="text">个人中心</div>
			</div>
		</div>
		<!--底部tab键 end-->
		
	</div>
</template>


<script>
	export default {
		data() {
			return {
				Router:this.$Router,
				showView: false,
				is_show:false,
				positionDate:[{},{},{},{},{}]
			}
		},
		onLoad() {
			const self = this;
			// self.$Utils.loadAll(['getMainData'], self);
		},
		methods: {
			getMainData() {
				const self = this;
				const postData = {};
				postData.tokenFuncName = 'getProjectToken';
				var callback = function(res){
				    console.log('getMainData', res);
				    self.mainData.push.apply(self.mainData,res.info.data);		        
				};
				self.$apis.orderGet(postData, callback);
			}
		},
	}
</script>


<style>
	@import "../../assets/style/public.css";
	@import "../../assets/style/navbar.css";
	@import "../../assets/style/workbench.css";
	@import "../../assets/style/adrss.css";
	
	page{padding-top:120rpx;padding-bottom: 140rpx;}
	.positionList li{border-bottom: 1px solid #eee;}
	.seachbox{padding: 15px 4%;background: #398EF9;position: fixed;top: 0px;left: 0;width: 100%;box-sizing: border-box;}
	.seachbox .Licon{width:13px; height: 13px; display: block;}
	.seachbox .rr{width: 70%;background:#fff;border-radius: 20px;overflow: hidden;}
	.seachbox .rr .input{width: 80%;}
	.seachbox .rr .input input{width: 100%;line-height: 30px;border-radius: 20px;padding: 0 10px;box-sizing: border-box;display: block;text-align: center; font-size: 26rpx;}
	.seachbox .rr .seachBtn{width: 20%;height: 30px; display: block;background: url(../../static/images/home-icon2.png) no-repeat center center/16px 16px;}

</style>

