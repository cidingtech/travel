<template>
	<div>
		<div class="recommend-title">热销推荐</div>
		<ul>
			<li class="item border-bottom" v-for="item of recommendList" :key="item.id">
				<img class="item-img" :src="item.imgUrl">
				<div class="item-info">
					<p class="item-title">{{item.title}}</p>
					<p class="item-desc">{{item.desc}}</p>
					<button class="item-btn">查看详情</button>
				</div>
			</li>
		</ul>
	</div>
</template>
<script>
	export default{
		name:'HomeRecommend',
		props:{
			recommendList:Array
		},
		data(){
			return{
				/*recommendList:[{
					id:'0001',
					img:'http://img1.qunarzz.com/sight/p0/1508/89/895a1b7add84f23faca053ce9e3153db.water.jpg_200x200_99ae30ee.jpg',
					title:'北京野生动物园',
					desc:'老虎狮子啥都有，一起玩耍吧'
				},{
					id:'0002',
					img:'http://img1.qunarzz.com/sight/p0/1508/89/895a1b7add84f23faca053ce9e3153db.water.jpg_200x200_99ae30ee.jpg',
					title:'北京野生动物园',
					desc:'老虎狮子啥都有，一起玩耍吧'
				},{
					id:'0003',
					img:'http://img1.qunarzz.com/sight/p0/1508/89/895a1b7add84f23faca053ce9e3153db.water.jpg_200x200_99ae30ee.jpg',
					title:'北京野生动物园',
					desc:'老虎狮子啥都有，一起玩耍吧'
				}]*/
			}
		}
	}
</script>
<style lang="stylus" scoped>
	@import '~stylePro/mixins.styl'
	.recommend-title
		margin-top:.2rem
		line-height:.8rem
		background:#eee
		text-indent:.2rem
	.item
		overflow:hidden
		display:flex
		height:1.9rem
		//background:red
		.item-img
			width:1.7rem
			height:1.7rem
			padding:.1rem
		.item-info
			flex:1
			padding:.1rem
			min-width:0/*这个比较神奇：当实际宽度大于最小宽度时候，使用最小宽度*/
		.item-title
			line-height:.54rem
			font-size:.32rem
			ellipsis()	
		.item-desc
			line-height:.4rem
			color:#ccc
			ellipsis()	
		.item-btn
			line-height:.44rem
			margin-top:.16rem
			background:#ff9300
			padding:0 .2rem
			border-radius:.06rem
			color:#fff
</style>