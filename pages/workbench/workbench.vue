<template>
	<div>
		
		<div class="tooling_indNav f5bj color6">
			<div class="list flexRowBetween">
				<div class="item" :class="curr==1?'on':''" @click="change('1')">待处理</div>
				<div class="item" :class="curr==2?'on':''" @click="change('2')">待面试</div>
				<div class="item" :class="curr==3?'on':''" @click="change('3')">已面试</div>
			</div>
		</div>
		
		<div v-show="curr==1">
			<div class="samllNav flex color6 fs13 bordB1">
				<span class="item" :class="num==1?'on':''" @click="chageSamll('1')">HR邀约</span>
				<span class="item" :class="num==2?'on':''" @click="chageSamll('2')">自己邀约</span>
			</div>
			
			<div class="positionList">
				<ul>
					<li>
						<div class="flexRowBetween pdtb15 pr mglr4">
							<span class="fxIcon"><img src="../../static/images/workbench-icon.png"/></span>
							<div class="flex ll">
								<img class="Lphoto" src="../../static/images/workbench-img.png" >
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
						<div class="inviter pdtb15 mglr4">
							<div class="flexRowBetween fs12">
								<div class="item left flex">
									<img class="userPhoto" src="../../static/images/position-img.png" >
									<div class="">
										<h2 class="ftn">章诗·科莱</h2>
										<p class="color6">15802945745</p>
									</div>
								</div>
								<div class="item right">
									<p>面试时间</p>
									<p>2019年6月20日</p>
								</div>
							</div>
							<div class="flexRowBetween pdt15 adrss">
								<p class="flex adrssTit fs12"><img class="adrsIcon mgr5" src="../../static/images/position-icon1.png"/>西安市雁塔区中投国际A座1802室</p>
								<div class="adrssIcon flexEnd">
									<img class="GpsIcon mgr15" src="../../static/images/workbench-icon2.png" >
								</div>
							</div>
						</div>
						
						<div class="btnB flexEnd center fs12 color6 pdtb15 mglr4">
							<span class="btn">放弃</span>
							<span class="btn on">接受面试</span>
						</div>
					</li>
					<li class="myself">
						<div class="flexRowBetween pdtb15 pr mglr4">
							<span class="fxIcon"><img src="../../static/images/workbench-icon1.png"/></span>
							<div class="flex ll">
								<img class="Lphoto" src="../../static/images/workbench-img.png" >
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
						<div class="pdlr4 flexEnd ing fs13 pdb10">等待HR响应</div>
					</li>
				</ul>
			</div>
		</div>
		
		<div v-show="curr==2">
			<div class="positionList">
				<ul>
					<li>
						<div class="flexRowBetween pdtb15 pr mglr4">
							<span class="fxIcon"><img src="../../static/images/workbench-icon.png"/></span>
							<div class="flex ll">
								<img class="Lphoto" src="../../static/images/workbench-img.png" >
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
						<div class="inviter pdtb15 mglr4">
							<div class="flexRowBetween fs12">
								<div class="item left flex">
									<img class="userPhoto" src="../../static/images/position-img.png" >
									<div class="">
										<h2 class="ftn">章诗·科莱</h2>
										<p class="color6">15802945745</p>
									</div>
								</div>
								<div class="item right">
									<p>面试时间</p>
									<p>2019年6月20日</p>
								</div>
							</div>
							<div class="flexRowBetween pdt15 adrss">
								<p class="flex adrssTit fs12"><img class="adrsIcon mgr5" src="../../static/images/position-icon1.png"/>西安市雁塔区中投国际A座1802室</p>
								<div class="adrssIcon flexEnd">
									<img class="GpsIcon mgr15" src="../../static/images/workbench-icon2.png" >
								</div>
							</div>
						</div>
						
						<div class="btnB flexEnd center fs12 color6 pdtb15 mglr4">
							<span class="btn" @click="delayShow">延期</span>
							<span class="btn">放弃</span>
							<span class="btn on">接受面试</span>
						</div>
					</li>
				</ul>
			</div>
		</div>
		
		<div v-show="curr==3">
			<div class="samllNav flex color6 fs13 bordB1">
				<span class="item" :class="num==1?'on':''" @click="chageSamll('1')">已通过</span>
				<span class="item" :class="num==2?'on':''" @click="chageSamll('2')">未通过</span>
				<span class="item" :class="num==3?'on':''" @click="chageSamll('3')">已放弃</span>
			</div>
			
			<div class="positionList">
				<ul>
					<li>
						<div class="flexRowBetween pdtb15 pr mglr4">
							<span class="fxIcon"><img src="../../static/images/workbench-icon1.png"/></span>
							<div class="flex ll">
								<img class="Lphoto" src="../../static/images/workbench-img.png" >
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
						<div class="ms-result flex mglr4 pdb15 fs12 color6">
							<span class="span one">未通过</span>
							<span class="span two">不合适</span>
							<span class="span three">不合适</span>
							<span class="span four">不合适</span>
						</div>
					</li>
					<li>
						<div class="flexRowBetween pdtb15 pr mglr4">
							<span class="fxIcon"><img src="../../static/images/workbench-icon.png"/></span>
							<div class="flex ll">
								<img class="Lphoto" src="../../static/images/workbench-img.png" >
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
						<div class="inviter pdtb15 mglr4">
							<div class="flexRowBetween fs12">
								<div class="item left flex">
									<img class="userPhoto" src="../../static/images/position-img.png" >
									<div class="">
										<h2 class="ftn">章诗·科莱</h2>
										<p class="color6">15802945745</p>
									</div>
								</div>
								<div class="item right">
									<p>面试时间</p>
									<p>2019年6月20日</p>
								</div>
							</div>
							<div class="flexRowBetween pdt15 adrss">
								<p class="flex adrssTit fs12"><img class="adrsIcon mgr5" src="../../static/images/position-icon1.png"/>西安市雁塔区中投国际A座1802室</p>
								<div class="adrssIcon flexEnd">
									<img class="GpsIcon mgr15" src="../../static/images/workbench-icon2.png" >
								</div>
							</div>
						</div>
						
						<div class="btnB flexEnd center fs12 color6 pdtb15 mglr4">
							<span class="btn">放弃</span>
							<span class="btn on">入职</span>
						</div>
					</li>
					
					<li>
						<div class="flexRowBetween pdtb15 pr mglr4">
							<span class="fxIcon"><img src="../../static/images/workbench-icon.png"/></span>
							<div class="flex ll">
								<img class="Lphoto" src="../../static/images/workbench-img.png" >
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
						
						<div class="btnB flexRowBetween center fs12 color6 pdb15 mglr4">
							<div class="pubColor">已通过&nbsp;·&nbsp;放弃</div>
							<div class="flexEnd">
								<a class="btn" href="workbench_evaluate.html">评价</a>
							</div>
						</div>
					</li>
					<li>
						<div class="flexRowBetween pdtb15 pr mglr4">
							<span class="fxIcon"><img src="../../static/images/workbench-icon.png"/></span>
							<div class="flex ll">
								<img class="Lphoto" src="../../static/images/workbench-img.png" >
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
						
						<div class="btnB flexRowBetween center fs12 color6 pdb15 mglr4">
							<div class="pubColor">已通过&nbsp;·&nbsp;入职</div>
							<div class="flexEnd">
								<!-- <a class="btn" href="#">评价</a> -->
							</div>
						</div>
					</li>
					
				</ul>
			</div>
		</div>
		
		<!-- 延期原因弹框 -->
		<div class="black-bj" v-show="is_show"></div>
		<div class="delayShow center whiteBj radius8" v-show="is_delayShow">
			<div class="RcolseBtn"  @click="delayShow">×</div>
			<p class="fs13 color6 pdb20 mgb5">拨打电话，告知原因</p>
			<p class="flexCenter">
				<img class="phoneIcon" src="../../static/images/workbence-icon1.png" >
				<em>029-36203569</em>
			</p>
		</div>
		
		<!--底部tab键-->
		<div class="navbar flexRowBetween">
			<div class="navbar_item flexColumn" @click="Router.navigateTo({route:{path:'/pages/workbench/workbench'}})">
				<div class="nav_img">
					<img src="../../static/images/nabar1-a.png" />
				</div>
				<div class="text this-text">工作台</div>
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
				curr:1,
				num:0,
				is_delayShow:false
			}
		},
		onLoad() {
			const self = this;
			// self.$Utils.loadAll(['getMainData'], self);
		},
		methods: {
			change(curr){
				const self = this;
				if(curr!=self.curr){
					self.curr = curr
				}
			},
			chageSamll(num){
				const self = this;
				if(num!=self.num){
					self.num = num
				}
			},
			delayShow(){
				const self = this;
				self.is_show = !self.is_show;
				self.is_delayShow =!self.is_delayShow
			},
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
	@import "../../assets/style/workbench.css";
	@import "../../assets/style/adrss.css";
	
	page{padding-bottom: 140rpx;}

</style>

