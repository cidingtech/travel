<template>
	<div>
		<div class="recommend-title">周末去哪</div>
		<ul>
			<li class="item border-bottom" v-for="item of weekendList" :key="item.id">
				<div class="item-img-wrapper">
					<img class="item-img" :src="item.imgUrl">
				</div>
				<div class="item-info">
					<p class="item-title">{{item.title}}</p>
					<p class="item-desc">{{item.desc}}</p>
				</div>
			</li>
		</ul>
	</div>
</template>
<script>
	export default{
		name:'HomeWeekend',
		props:{
			weekendList:Array
		},
		data(){
			return{
				/*weekendList:[{
					id:'0001',
					img:'http://img1.qunarzz.com/sight/source/1505/53/02091f1ee43d0a.jpg_r_640x214_2e3256b1.jpg',
					title:'北京野生动物园',
					desc:'老虎狮子啥都有，一起玩耍吧'
				},{
					id:'0002',
					img:'http://img1.qunarzz.com/sight/source/1505/aa/7baaf8a851d221.jpg_r_640x214_1431200f.jpg',
					title:'北京野生动物园',
					desc:'老虎狮子啥都有，一起玩耍吧'
				},{
					id:'0003',
					img:'http://img1.qunarzz.com/sight/source/1505/9e/21df651e19af5d.jpg_r_640x214_3ea5bb38.jpg',
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
		line-height:.8rem
		background:#eee
		text-indent:.2rem
	.item-img-wrapper
		overflow:hidden
		height:0
		padding-bottom:37.09%
		.item-img
			width:100% 
	.item-info
		padding:.1rem
		.item-title
			line-height:.54rem
			font-size:.32rem
			ellipsis()	
		.item-desc
			line-height:.4rem
			color:#ccc
			ellipsis()	
</style>