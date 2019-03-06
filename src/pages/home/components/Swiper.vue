<template>
	<div class="wrapper">
		<swiper :options="swiperOption" v-if="showSwiper">
		    <swiper-slide v-for="item of swiperList" :key="item.id">
		    	<img class="swiper-img" :src="item.imgUrl">
		    </swiper-slide>
		    <div class="swiper-pagination" slot="pagination"></div>
		</swiper>
	</div>
</template>
<script>
	export default {
		name:'HomeSwiper',
		props:{
			swiperList:Array
		},
		data(){
			return{
				swiperOption:{
					pagination:'.swiper-pagination',
					loop:true
				},
				/*swiperList:[{
					id:'0001',
					imgUrl:'http://img1.qunarzz.com/piao/fusion/1807/66/e5a5cec881702f02.jpg_750x200_67bb5691.jpg'
				},{
					id:'0002',
					imgUrl:'http://img1.qunarzz.com/piao/fusion/1806/1c/4847ea66072c7b02.jpg_750x200_c32457fb.jpg'
				}]*/
			}
		},
		computed:{
			showSwiper(){
				return this.swiperList.length
			}
		}
	}
</script>
<style lang="stylus" scoped>
	.wrapper >>> .swiper-pagination-bullet-active
		background:#fff
	.wrapper
		overflow:hidden/*这两句height0和overflow和padding-bottom结合作用是使图片能自适应宽高比640:200约等于26.67，如果将26.67%直接写在height里不是相对高度而言的，所以这种方式是基于宽度把高度撑开26.67%，保证自适应！*/
		width:100%
		height:0
		padding-bottom:31.67%
		background:#eee
		.swiper-img
			width:100%
	
		
</style>