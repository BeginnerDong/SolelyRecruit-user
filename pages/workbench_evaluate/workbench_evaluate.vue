<template>
	<div>
		
		<div class="pdlr4">
			<div class="pingjia flex center pdt20 fs13">
				<span class="btn" :class="{on:item.bOn}" @click="checkBox(index)" v-for="(item,index) in pjLableData"  :key="index">{{item.title}}</span>
			</div>
			<div class="submitbtn" style="margin-top: 100px;">
				<button type="button" class="btn" :key="index" @click="Router.navigateTo({route:{path:'/pages/workbench/workbench'}})">确定</button>
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
				pjLableData:[
					{title:'不合适',bOn:false},
					{title:'不合适',bOn:false},
					{title:'不合适',bOn:false},
					{title:'不合适',bOn:false},
					{title:'不合适',bOn:false},
					{title:'不合适',bOn:false},
					{title:'不合适',bOn:false},
					{title:'不合适',bOn:false},
					{title:'不合适',bOn:false},
					{title:'不合适',bOn:false}
				]
			}
		},
		onLoad() {
			const self = this;
			// self.$Utils.loadAll(['getMainData'], self);
		},
		methods: {
			checkBox(i){
				const self = this;
				self.pjLableData[i].bOn = !self.pjLableData[i].bOn
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
	
	.pingjia{flex-wrap: wrap;}
	.pingjia .btn{width:30%; line-height: 30px;margin-right: 5%;margin-bottom: 20px;border:1px solid #eee;border-radius: 4px;box-sizing: border-box;}
	.pingjia .btn:nth-of-type(3n){margin-right: 0;}
	.pingjia .btn.on{background: #398EF9; color: #fff;border-color: #398EF9;}
	
</style>

