<template>
	<div>
		
		<div class="userHead flexRowBetween">
			<div class="ll">
				<h1 class="fs22 mgb5">张望</h1>
				<p class="fs12 color6">还没有填写个人介绍</p>
			</div>
			<div class="flexEnd">
				<img class="Rphoto" src="../../static/images/position-img.png"/>
			</div>
		</div>
		<div class="f5H10"></div>
		
		<div class="XlineNav">
			<div class="info mglr4 pdtb15 flexRowBetween bordB1" @click="Router.navigateTo({route:{path:'/pages/user_myResume/user_myResume'}})">
				<div class="flex">
					<img class="icon" src="../../static/images/about-icon.png">
					<span class="tt">我的简历</span>
				</div>
				<div class="right flexEnd">
					<img class="arrowR" src="../../static/images/information-icon1.png" >
				</div>
			</div>
			<div class="info mglr4 pdtb15 flexRowBetween bordB1" @click="Router.navigateTo({route:{path:'/pages/company/company'}})">
				<div class="flex">
					<img class="icon" src="../../static/images/about-icon1.png">
					<span class="tt">公司</span>
				</div>
				<div class="right flexEnd">
					<img class="arrowR" src="../../static/images/information-icon1.png" >
				</div>
			</div>
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
					<img src="../../static/images/nabar2.png" />
				</div>
				<div class="text">职位</div>
			</div>
			<div class="navbar_item" @click="Router.navigateTo({route:{path:'/pages/tidings/tidings'}})">
				<div class="nav_img">
					<img src="../../static/images/nabar3.png" />
				</div>
				<div class="text">消息</div>
			</div>
			<div class="navbar_item" @click="Router.navigateTo({route:{path:'/pages/user/user'}})">
				<div class="nav_img">
					<img src="../../static/images/nabar4-a.png" />
				</div>
				<div class="text this-text">个人中心</div>
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
				is_show:false
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
	@import "../../assets/style/NavTab.css";
	
	.userHead{padding: 25px 4%;}
	.userHead .ll{ width: 80%;}
	.userHead .Rphoto{width: 60px; height: 60px;border-radius: 50%;display: block;}
	.XlineNav .icon{width: 15px;height: 15px;margin-right: 10px; display: block;}
	
</style>

