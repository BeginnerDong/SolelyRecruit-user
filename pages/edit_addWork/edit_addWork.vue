<template>
	<div>
		
		<div class="myRowBetween pdlr4">
			<div class="item pdtb15 flexRowBetween bordB1">
				<span class="ll">公司名称</span>
				<div class="flexEnd rr" style="width: 50%;">
					<input type="text" name="" id="" value="" placeholder="请输入公司名称" />
				</div>
			</div>
			<div class="item pdtb15 flexRowBetween bordB1">
				<span class="ll">你的职称</span>
				<span class="flexEnd color6 fs13" @click="seltShow">请选择<img class="arrowR" src="../../static/images/information-icon1.png" ></span>
			</div>
			
			<div class="item pdtb15 flexRowBetween bordB1">
				<span class="ll">入职时间</span>
				<span class="flexEnd color6 fs13">请选择<img class="arrowR" src="../../static/images/information-icon1.png" ></span>
			</div>
			<div class="item pdtb15 flexRowBetween bordB1">
				<span class="ll">离职时间</span>
				<span class="flexEnd color6 fs13">请选择<img class="arrowR" src="../../static/images/information-icon1.png" ></span>
			</div>
			<div class="item pdtb15">
				<p class="ll pdb10">工作内容</p>
				<div class="f5bj">
					<textarea style="height: 150px;" rows="" cols="" placeholder="请输入认知期间的工作内容" value=""></textarea>
				</div>
			</div>
		</div>
		
		<div class="submitbtn" style="margin-top: 60px;">
			<button class="btn" type="button">保存</button>
		</div>
		
		<div class="black-bj" v-show="is_show"></div>
		<div class="seltShow radius8 whiteBj" v-show="is_seltShow">
			<div class="RcolseBtn" @click="seltShow">×</div>
			<p class="tt">会计</p>
			<p class="tt">会计助理</p>
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
				is_seltShow:false
			}
		},
		onLoad() {
			const self = this;
			// self.$Utils.loadAll(['getMainData'], self);
		},
		methods: {
			seltShow(){
				const self = this;
				self.is_show = !self.is_show;
				self.is_seltShow = !self.is_seltShow;
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
	@import "../../assets/style/editInfor.css";

</style>

