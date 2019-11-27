<template>
	<div>
		
		<!-- 公司名称 -->
		<div class="pdlr4">
			<div class="compyCont pdtb15 flexRowBetween">
				<div class="ll">
					<h2 class="pdb5 fs20 ftn mgb5">华建博文</h2>
					<p class="fs13 color6">西安&nbsp;/&nbsp;金融,电商&nbsp;/&nbsp;上市公司&nbsp;/&nbsp;2000人以上</p>
				</div>
				<div class="rr flexEnd">
					<img class="compyLogo" src="../../static/images/message-img.png" >
				</div>
			</div>
		</div>
		<div class="f5H5"></div>
		<div class="pdlr4">
			<div class="orderNav bordB1">
				<span class="tt" :class="curr==1?'on':''" @click="changeCurr('1')">公司主页</span>
				<span class="tt" :class="curr==2?'on':''" @click="changeCurr('2')">在招职位</span>
			</div>
			
			<div v-show="curr==1">
				<div class="xqInfor">
					<h1 class="fs14 center pdtb15">公司简介</h1>
					<div class="cont fs13 line24">
						<p>中国金融界康师傅了十多个价格付款受打击了回家开了个人或收到了话估计发的是供货方人生规划牢四个规划局发生过回个话临时工供货方就是个多少个和规范化故事馆如果让两个挂号费就开始过份了苟富贵换个方式，发个电话撒发几个咖啡。</p>
						<img src="../../static/images/details-img.png" >
					</div>
					
					<h1 class="fs14 center pdtb15">公司地址</h1>
					<div class="flexRowBetween pdb15 adrss mglr4">
						<p class="flex adrssTit fs13 color6"><img class="adrsIcon mgr5" src="../../static/images/position-icon1.png"/>西安市雁塔区中投国际A座1802室</p>
						<div class="adrssIcon flexEnd">
							<img class="GpsIcon" src="../../static/images/workbench-icon2.png" >
						</div>
					</div>
				</div>
			</div>
			
			<div v-show="curr==2">
				<div class="jobClass flex fs12 center">
					<span class="item on">全部(56)</span>
					<span class="item">技术</span>
					<span class="item disabled">产品</span>
					<span class="item">设计</span>
					<span class="item disabled">运营</span>
					<span class="item">市场</span>
					<span class="item disabled">销售</span>
					<span class="item disabled">职能</span>
					<span class="item">财务</span>
					<span class="item disabled">其他</span>
				</div>
				<div class="jobList mgt10">
					<ul>
						<li class="pdtb15 flexRowBetween" v-for="(item,index) in jobList"  @click="Router.navigateTo({route:{path:'/pages/positionDetail/positionDetail'}})">
							<div class="ll">
								<h2 class="ftn">前端工程师</h2>
								<p class="fs12 color9 mgt5">西安/应届生/学历不限</p>
							</div>
							<div class="rr ftr">
								<p class="red">6K-8K</p>
								<p class="mgt5 fs12 color9">11.12发布</p>
							</div>
						</li>
					</ul>
				</div>
			</div>
		</div>
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
				jobList:[{},{},{},{},{}]
			}
		},
		onLoad() {
			const self = this;
			// self.$Utils.loadAll(['getMainData'], self);
		},
		methods: {
			changeCurr(curr){
				const self = this;
				if(curr!=self.curr){
					self.curr = curr
				}
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
	@import "../../assets/style/NavTab.css";
	@import "../../assets/style/company.css";
	@import "../../assets/style/prodctDetail.css";
	@import "../../assets/style/adrss.css";
	
	.jobClass{flex-wrap: wrap;}
	.jobClass .item{padding: 0 8px;min-width: 50px;box-sizing: border-box;line-height: 30px;border-radius: 20px; margin-right:15px;border:1px solid #eee;margin-top: 15px;}
	.jobClass .item.on{background: #398EF9; border-color: #398EF9;color: #fff;}
	.jobClass .item.disabled{color: #d4d4d4;}
	.jobList li{border-bottom: 1px solid #eee;}

</style>

