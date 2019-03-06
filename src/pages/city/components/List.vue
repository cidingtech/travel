<template>
  <div class="list" ref="wrapper">
  	<div>
	  	<div class="area">
	  		<div class="title border-topbottom">当前城市</div>
	  		<div class="button-list">
	  			<div class="button-wrapper">
	  				<div class="button">北京</div>
	  			</div>
	  			<div class="button-wrapper">
	  				<div class="button">北京</div>
	  			</div>
	  			<div class="button-wrapper">
	  				<div class="button">北京</div>
	  			</div>
	  		</div>
	  	</div>
	  	<div class="area">
	  		<div class="area">
		  		<div class="title border-topbottom">热门城市</div>
		  		<div class="button-list">
		  			<div class="button-wrapper" :key="item.id" v-for="item of hot">
		  				<div class="button">{{item.name}}</div>
		  			</div>
		  		</div>
		  	</div>
	  	</div>
	  	<div class="area" v-for="(item, key) of citys" :key="key" :ref="key">
	  		<div class="title border-topbottom">{{key}}</div>
	  		<div class="item-list">
	  			<div class="item border-bottom" v-for="childItem of item" :key="childItem.id">{{childItem.name}}</div>
	  		</div>
	  	</div>
	</div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
  name: 'CityList',
  props:{
  	hot:Array,
  	citys:Object,
  	letter:String
  },
  mounted(){
  	console.log(this.citys)
  	this.scroll = new BScroll(this.$refs.wrapper)
  },
  watch:{
  	letter(){
  		console.log(this.letter)
  		if(this.letter){
  			this.scroll.scrollToElement(this.$refs[this.letter][0])
  		}
  	}
  }
}
</script>

<style lang="stylus" scoped>
	.border-topbottom
		&:before
			border-color:#ccc
		&:after
			border-color:#ccc
	.border-bottom
		&:before
			border-color:#ccc
	.list
		overflow:hidden
		position:absolute
		top:1.58rem
		bottom:0
		left:0
		right:0
		.title
			line-height:.44rem
			background:#eee
			padding-left:.3rem
			color:#666
			font-size:.26rem
		.button-list
			overflow: hidden
			padding:.1rem .6rem .1rem .1rem
			.button-wrapper
				float:left
				width:33.33%
				.button
					text-align:center
					margin:.1rem
					padding:.1rem 0
					border-radius:.06rem
					border:.02rem solid #ccc
		.item-list
			.item
				line-height:.66rem
				padding-left:.2rem		
			
</style>
