<template>
  <div class="hd">
    <div class="hd-left"><div class="iconfont back-icon">&#xe624;</div></div>
    <div class="hd-center"><span class="iconfont">&#xe632;</span>输入城市景点游玩主题</div>
    <router-link to="/city">
    	<div class="hd-right">{{this.city}}<span class="iconfont city-icon">&#xe64a;</span></div>
  	</router-link>
  </div>
</template>

<script>
export default {
  name: 'HeaderHeader',
  props:{
  	city:String
  }
}
</script>

<style lang="stylus" scoped>
	@import '~stylePro/varibles.styl'
	.hd
		height:$headerHeight
		display:flex
		line-height:$headerHeight
		background:$bgColor
		color:#fff
		.hd-left
			float:left
			width:.64rem
			.back-icon
				text-align:center
				font-size:.4rem
		.hd-center
			flex:1
			height:.64rem
			margin:.13rem 
			background:#fff
			border-radius:.1rem
			color:#ccc
			line-height:.64rem
			padding-left:.2rem
		.hd-right
			color:#fff
			float:right
			width:1rem
			.city-icon
				font-size:.2rem
				margin-left:.1rem
			
</style>
