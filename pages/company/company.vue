<template>
	<div>
		
		<!-- 公司名称 -->
		<div class="pdlr4 compyCont">
			<ul>
				<li v-for="(item,index) in compayData" :key="index" @click="Router.navigateTo({route:{path:'/pages/companyDetail/companyDetail'}})">
					<div class="flexRowBetween">
						<div class="ll">
							<h2 class="pdb5 fs16">华建博文</h2>
							<p class="fs12 color6">西安&nbsp;/&nbsp;移动互联网,企业服务&nbsp;/&nbsp;在招职位&nbsp;/&nbsp;</p>
						</div>
						<div class="rr flexEnd">
							<img class="compyLogo" src="../../static/images/message-img.png" >
						</div>
					</div>
					<div class="flex fs12 mgt5">
						<img class="HRphoto" src="../../static/images/company-img.png"/>
						<span class="name mglr5">李莉<em class="dian">·</em>HR</span>
						<span class="lab">6256<em class="dian">·</em>曝光度</span>
					</div>
				</li>
			</ul>
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
				compayData:[{},{},{},{},{},{}]
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
	@import "../../assets/style/company.css";
	

</style>

