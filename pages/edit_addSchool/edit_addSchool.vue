<template>
	<div>
		
		<div class="myRowBetween pdlr4">
			<div class="item pdtb15 flexRowBetween bordB1">
				<span class="ll">学校名称</span>
				<div class="flexEnd rr" style="width: 50%;">
					<input type="text" name="" id="" value="" placeholder="请输入学校名称" />
				</div>
			</div>
			<div class="item pdtb15 flexRowBetween bordB1">
				<span class="ll">学历</span>
				<span class="flexEnd color6 fs13" @click="seltShow">请选择<img class="arrowR" src="../../static/images/information-icon1.png" ></span>
			</div>
			
			<div class="item pdtb15 flexRowBetween bordB1">
				<span class="ll">专业</span>
				<div class="flexEnd rr" style="width: 50%;">
					<input type="text" name="" id="" value="" placeholder="请输入专业" />
				</div>
			</div>
			<div class="item pdtb15 flexRowBetween bordB1">
				<span class="ll">入学年份</span>
				<span class="flexEnd color6 fs13">请选择<img class="arrowR" src="../../static/images/information-icon1.png" ></span>
			</div>
			<div class="item pdtb15 flexRowBetween bordB1">
				<span class="ll">毕业年份</span>
				<span class="flexEnd color6 fs13">请选择<img class="arrowR" src="../../static/images/information-icon1.png" ></span>
			</div>
		</div>
		
		<div class="submitbtn" style="margin-top: 80px;">
			<button class="btn" type="button">保存</button>
		</div>
		
		<!-- 选项弹框 -->
		<div class="black-bj" v-show="is_show"></div>
		<div class="seltShow radius8 whiteBj" v-show="is_seltShow">
			<div class="RcolseBtn" @click="seltShow">×</div>
			<p class="tt">博士</p>
			<p class="tt">研究生</p>
			<p class="tt">本科</p>
			<p class="tt">大专</p>
			<p class="tt">高中</p>
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

