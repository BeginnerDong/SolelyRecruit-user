<template>
	<div>
		
		<div class="pdlr4">
			<div class="center ingTalk flexCenter mgtb20"><span class="tit radius5 fs13 color6">正在沟通的职位：会计助理</span></div>
			
			<div class="currJob whiteBj radius8 pd15">
				<div class="flexRowBetween">
					<h1 class="name fs14">会计助理</h1>
					<div class="red flexEnd">4K-6K</div>
				</div>
				<p class="lable fs13 color6 pdt5 pdb5">克莱</p>
				<p class="fs12 color9">西安&nbsp;|&nbsp;3年&nbsp;|&nbsp;本科</p>
			</div>
			
			<div class="dialogBox">
				<div class="item right">
					<div class="time center fs13 color9">14:23</div>
					<div class="infor">
						<p class="text">你好，我已有1年的工作经验，现任职位会计助理，对贵公司该职位很感兴趣，希望能与你进一步沟通。</p>
						<img class="Photo" src="../../static/images/position-img.png" >
					</div>
				</div>
				<div class="item left">
					<div class="time center fs13 color9">14:23</div>
					<div class="infor">
						<img class="Photo" src="../../static/images/company-img.png" >
						<p class="text">你好，想和你详细沟通下，现在方便吗？</p>
					</div>
				</div>
			</div>
		</div>
		
		<div class="fix-talkIput flexRowBetween">
			<div class="input">
				<input type="text">
			</div>
			<button class="send" type="button">发送</button>
		</div>
		
		
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
	/* @import "../../assets/style/navbar.css"; */
	
	page{padding-bottom: 70px;background: #F5F5F5;}
	.ingTalk .tit{padding: 0 15px;line-height: 30px;background: #ebebeb;}
	.dialogBox .infor{align-items: flex-start;}
	.dialogBox .item .time{padding: 30px 0 15px 0;}
	.dialogBox .infor .Photo{ width: 45px; height: 45px;display: block;border-radius: 50%;}
	.dialogBox .infor .text{max-width: 240px;padding: 10px;border-radius: 8px; line-height: 24px;position: relative;}
	
	.dialogBox .right .Photo{margin-left: 10px;}
	.dialogBox .right .infor{display: flex; justify-content: flex-end;}
	.dialogBox .right .infor .text{background: #45b289; color: #fff;}
	.dialogBox .right .infor .text:after{content: '';position: absolute;top:10px;right:-7px;width:0;height:0;border-top:8px solid transparent;border-bottom:8px solid transparent; border-left:8px solid #45b289;}
	
	.dialogBox .left .Photo{margin-right: 10px;}
	.dialogBox .left .infor{display: flex; justify-content: flex-start;}
	.dialogBox .left .infor .text{background: #fff; color: #333;}
	.dialogBox .left .infor .text:after{content: '';position: absolute;top:10px;left:-7px;width:0;height:0;border-top:8px solid transparent;border-bottom:8px solid transparent; border-right:8px solid #fff;}
	
	.fix-talkIput{padding: 15px 5%;border-top: 1px solid #eee;position: fixed; bottom: 0;left: 0;width: 100%;box-sizing: border-box;}
	.fix-talkIput .input{width: 80%;}
	.fix-talkIput .input input{width: 100%;height: 30px;line-height: 30px;display: block;font-size: 13px;background: #fff;border:1px solid #eee; border-radius: 8px;padding: 0 10px;box-sizing: border-box;}
	.fix-talkIput .send{width: 18%;height: 28px;line-height: 28px;text-align: center;color: #fff;border-radius: 4px;background: #398EF9;margin-left: 2%; font-size: 14px;}
	
</style>

