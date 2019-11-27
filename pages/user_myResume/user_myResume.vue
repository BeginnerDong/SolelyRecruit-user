<template>
	<div>
		
		
		<div class="mglr4 pdtb15">
			<div class="flexRowBetween">
				<h1 class="fs18 mgb10">张尚恩</h1>
				<div class="flexEnd pubColor fs12" @click="Router.navigateTo({route:{path:'/pages/edit_userInfor/edit_userInfor'}})"><img class="sallIcon mgr5" src="../../static/images/resume-icon3.png"/>编辑</div>
			</div>
			
			<div class="flex fs13 color6">
				<span>女</span>&nbsp;/&nbsp;<span>22岁</span>&nbsp;/&nbsp;<span>西安市</span>&nbsp;/&nbsp;<span>2年</span>&nbsp;/&nbsp;<span>职场人事</span>
			</div>
			<div class="mgt5 flex mgt15 mgb10 fs13"><img class="sallIcon mgr5" src="../../static/images/resume-icon.png" >15689562325</div>
			<div class="mgt5 flex fs13"><img class="sallIcon mgr5" src="../../static/images/resume-icon1.png" >nengmenhhn@163.com</div>
		</div>
		<div class="f5H5"></div>
		
		<!-- 教育经历 -->
		<div class="pdlr4">
			<h1 class="pdt15">教育经历</h1>
			<div class="positionList jiaoyu">
				<ul>
					<li class="flexRowBetween pdtb15">
						<div class="flex ll">
							<img class="Lphoto" src="../../static/images/home-img.png" >
							<div class="infor">
								<h1 class="name fs15">陕西科技大学</h1>
								<p class="lable fs12 color6">本科/会计</p>
								<p class="fs12 color9 ">2014-2018</p>
							</div>
						</div>
						<div class="rr flexEnd">
							<div class="flexEnd pubColor fs12" @click="Router.navigateTo({route:{path:'/pages/edit_addSchool/edit_addSchool'}})"><img class="sallIcon mgr5" src="../../static/images/resume-icon3.png" >编辑</div>
						</div>
					</li>
				</ul>
			</div>
			<div class="pdtb15 flexCenter ">
				<span class="flex" @click="Router.navigateTo({route:{path:'/pages/edit_addSchool/edit_addSchool'}})"><img class="sallIcon mgr5" src="../../static/images/resume-icon4.png" >添加教育经历</span>
			</div>
		</div>
		<div class="f5H5"></div>
		
		<!-- 工作经历 -->
		<div class="pdlr4">
			<h1 class="pdt15">工作经历</h1>
			<div class="positionList">
				<ul>
					<li class="pdtb15">
						<div class="flexRowBetween">
							<div class="flex ll">
								<img class="Lphoto" src="../../static/images/home-img.png" >
								<div class="infor">
									<h1 class="name fs14">会计助理</h1>
									<p class="lable fs12 color6">纯粹科技</p>
									<p class="fs12 color9 ">2018.10-至今</p>
								</div>
							</div>
							<div class="rr flexEnd">
								<div class="flexEnd pubColor fs12" @click="Router.navigateTo({route:{path:'/pages/edit_addWork/edit_addWork'}})"><img class="sallIcon mgr5" src="../../static/images/resume-icon3.png" >编辑</div>
							</div>
						</div>
						<div class="fs13 pdb5 pdt10">工作内容</div>
						<div class="fs12 color6">欧冠怕个个都是孤独鳏寡火箭发射刘红革鸽供货方几点开始个供货方简单说李海峰是考虑光和热计算机。</div>
					</li>
				</ul>
			</div>
			<div class="pdtb15 flexCenter ">
				<div class="flex" @click="Router.navigateTo({route:{path:'/pages/edit_addWork/edit_addWork'}})"><img class="sallIcon mgr5" src="../../static/images/resume-icon4.png" >添加工作经历</div>
			</div>
		</div>
		<div class="f5H5"></div>
		<div class="pdlr4">
			<h1 class="pdtb15">上传图集</h1>
			<div class="upImgbox flex bordB1">
				<div class="item pr">
					<div class="colse">×</div>
					<img class="pic" src="../../static/images/resume-img.png" >
				</div>
				<div class="item pr">
					<div class="colse">×</div>
					<img class="pic" src="../../static/images/resume-img.png" >
				</div>
				<div class="item pr">
					<div class="colse">×</div>
					<img class="pic" src="../../static/images/resume-img.png" >
				</div>
				<div class="item pr">
					<div class="colse">×</div>
					<img class="pic" src="../../static/images/resume-img.png" >
				</div>
			</div>
			<div class="pdtb15 flexCenter ">
				<div class="flex pr" href="#">
					<img class="sallIcon mgr5" src="../../static/images/resume-icon4.png" >
					<p>上传图集</p>
					<input class="addUpBtn" type="file" value="" name="">
				</div>
			</div>
		</div>
		<div class="f5H5"></div>
		
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
	@import "../../assets/style/workbench.css";
	
	page{padding-bottom: 50px;}
	.sallIcon{width: 14px; height: 14px; display: block;}
	.positionList li{border-bottom: 1px solid #eee; align-items: flex-start;}
	.positionList li .ll{align-items: flex-start;}
	.positionList li .ll .Lphoto{width: 50px; height: 50px;}
	.jiaoyu ul li .ll .Lphoto{border-radius: 50%;}
	
	/* 上传图集 */
	.upImgbox{ flex-wrap: wrap;}
	.upImgbox .item{width: 110px; height:75px;margin: 0 2% 15px 0;}
	.upImgbox .item:nth-of-type(3n){margin-right: 0;}
	.upImgbox .item .pic{width: 100%; height: 100%; display: block;}
	.upImgbox .item .colse{width: 14px; height:14px; border-radius: 50%;color: #fff; background: rgba(0,0,0,0.5);position: absolute; top: -7px;right: -2px;text-align: center; line-height: 14px;}
	.addUpBtn{width: 100%; height: 100%; position: absolute; top: 0;left: 0;right: 0; bottom: 0; display: block; opacity: 0;}
</style>

