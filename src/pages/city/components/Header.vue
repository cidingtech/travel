<template>
  <div class="hd">
    城市选择
    <router-link to="/">
	    <div class="iconfont header-back">&#xe624;</div>
	</router-link>
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
	@import '~stylePro/varibles.styl'
	.hd
		position:relative
		height:$headerHeight
		line-height:$headerHeight
		text-align:center
		color:#fff
		background:$bgColor
		font-size:.3rem
		.header-back
			position:absolute
			top:0
			text-align:center
			font-size:.4rem
			width:.64rem
			text-align:center
			font-size:.4rem
			color:#fff
</style>
