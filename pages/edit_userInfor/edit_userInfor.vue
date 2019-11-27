<template>
	<div>
		
		<div class="myRowBetween pdlr4">
			<div class="item pdtb15 flexRowBetween bordB1">
				<span class="ll">照片</span>
				<div class="flexEnd eidtUpImg pr">
					<img class="pic" src="../../static/images/information-icon.png" >
					<input class="upBtn" type="file" name="" id="" value="" />
				</div>
			</div>
			<div class="item pdtb15 flexRowBetween bordB1">
				<span class="ll">真实姓名</span>
				<div class="flexEnd rr" style="width: 50%;">
					<input type="text" name="" id="" value="" placeholder="请输入真实姓名" />
				</div>
			</div>
			<div class="item pdtb15 flexRowBetween bordB1">
				<span class="ll">性别</span>
				<span class="flexEnd color6 fs13" @click="seltShow">请选择<img class="arrowR" src="../../static/images/information-icon1.png" ></span>
			</div>
			
			<div class="item pdtb15 flexRowBetween bordB1">
				<span class="ll">出生年月</span>
				<span class="flexEnd color6 fs13" >请选择<img class="arrowR" src="../../static/images/information-icon1.png" ></span>
			</div>
			<div class="item pdtb15 flexRowBetween bordB1">
				<span class="ll">当前身份</span>
				<span class="flexEnd color6 fs13">请选择<img class="arrowR" src="../../static/images/information-icon1.png" ></span>
			</div>
			<div class="item pdtb15 flexRowBetween bordB1">
				<span class="ll">参加工作时间</span>
				<span class="flexEnd color6 fs13">请选择<img class="arrowR" src="../../static/images/information-icon1.png" ></span>
			</div>
			<div class="item pdtb15 flexRowBetween bordB1">
				<span class="ll">手机号码</span>
				<div class="flexEnd color6 fs13 rr">
					<input type="number" value="" placeholder="请输入手机号码">
				</div>
			</div>
			<div class="item pdtb15 flexRowBetween bordB1">
				<span class="ll">联系邮箱</span>
				<div class="flexEnd color6 fs13 rr">
					<input type="text" value="" placeholder="请输入联系邮箱">
				</div>
			</div>
			<div class="item pdtb15 flexRowBetween bordB1">
				<span class="ll">所在城市</span>
				<span class="flexEnd color6 fs13">请选择<img class="arrowR" src="../../static/images/information-icon1.png" ></span>
			</div>
			
		</div>
		
		<div class="submitbtn" style="margin-top: 80px;">
			<button class="btn" type="button">保存</button>
		</div>
		
		<div class="black-bj" v-show="is_show"></div>
		<div class="seltShow radius8 whiteBj" v-show="is_seltShow">
			<div class="RcolseBtn" @click="seltShow">×</div>
			<p class="tt">男</p>
			<p class="tt">女</p>
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

