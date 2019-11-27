<template>
	<div>
		
		<div class="tidingLists pdlr4">
			<ul>
				<li v-for="(item,index) in tidingData" class="flexRowBetween pdt15">
					<div class="Lphoto">
						<img src="../../static/images/message-img.png" >
					</div>
					<div class="Rinfor bordB1 pdb15" @click="Router.navigateTo({route:{path:'/pages/tidingsDetail/tidingsDetail'}})">
						<p class="avoidOverflow3">你好,我已有1年工作经验，自合法化法律和覅挥发分混分巨发货饭到啦发哈积分自合法化法律和覅挥发分混分巨发货饭到啦发哈积分...</p>
						<p class="color6 fs13 pdt10 flexRowBetween">
							<span>墨之方科技</span>
							<span class="color9">14:16</span>
						</p>
					</div>
				</li>
			</ul>
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
					<img src="../../static/images/nabar3-a.png" />
				</div>
				<div class="text this-text">消息</div>
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
				tidingData:[{},{},{},{},{}]
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
	
	page{padding-bottom: 70px;}
	.tidingLists li{ align-items: flex-start;}
	.tidingLists .Lphoto{width: 18%;}
	.tidingLists .Lphoto img{width: 50px; height: 50px;display: block;}
	.tidingLists .Rinfor{width: 82%;}
	
</style>

