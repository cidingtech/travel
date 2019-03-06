<template>
	<div class="icons">
		<swiper :options="swiperOption" >
		    <swiper-slide v-for="(page, index) of pages" :key="index">
				<div class="icon" v-for="item of page" :key="item.id">
					<div class="icon-img">
						<img class="icon-img-con" :src="item.img">
					</div>
					<p class="icon-desc">{{item.desc}}</p>
				</div>
			</swiper-slide>
		</swiper>
	</div>
</template>
<script>
	export default {
		name:'HomeIcons',
		props:{
			iconList:Array
		},
		data(){
			return{
				swiperOption:{
					autoplay:false
				}
				/*iconList:[{
					id:'0001',
					desc:'景点门票',
					img:'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png'
				},{
					id:'0002',
					desc:'滑雪体验',
					img:'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png'
				},{
					id:'0003',
					desc:'滑雪体验',
					img:'http://img1.qunarzz.com/piao/fusion/1803/95/8246f27355943202.png'
				},{
					id:'0004',
					desc:'爬山破',
					img:'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png'
				},{
					id:'0005',
					desc:'滑草场',
					img:'http://img1.qunarzz.com/piao/fusion/1803/6a/45f595250c73d102.png'
				},{
					id:'0006',
					desc:'游泳',
					img:'http://img1.qunarzz.com/piao/fusion/1803/6c/9e54a8540fee0102.png'
				},{
					id:'0007',
					desc:'篮球',
					img:'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png'
				},{
					id:'0008',
					desc:'排球',
					img:'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png'
				},{
					id:'0009',
					desc:'一日游',
					img:'http://img1.qunarzz.com/piao/fusion/1803/95/8246f27355943202.png'
				}]*/
			}
		},
		computed:{
			pages(){
				const pages = []
				this.iconList.forEach((item, index) => {
					const page = Math.floor(index / 8)
					if(!pages[page]){
						pages[page] = []
					}
					pages[page].push(item)
				})
				return pages
			}
		}
	}
</script>
<style lang="stylus" scoped>
	@import '~stylePro/varibles.styl'
	@import '~stylePro/mixins.styl'
	.icons >>> .swiper-container
		/*overflow:hidden这里所有样式原来在icons上面,因为中间logo能触摸滑动的高度不对劲所以改成icons下面的样式使用在这里overflow隐藏是应为那个swiper插件自带这个样式*/
		height:0
		padding-bottom:50%
	.icons 
		margin-top:.2rem
		.icon
			position:relative
			overflow:hidden
			float:left
			width:25%
			padding-bottom:25%
			height:0
			.icon-img
				position:absolute
				top:0
				left:0
				right:0
				bottom:.44rem
				.icon-img-con
					display:block
					margin:0 auto
					height:100%
			.icon-desc
				color:$textColor
				position: absolute
				bottom: 0
				text-align: center
				left: 0
				right: 0
				height: 0.44rem
				line-height: 0.44rem
				ellipsis()

			
				
</style>