<template>
  <div class="search">
    <input type="text" class="search-input" placeholder="输入城市名或者拼音">
  </div>
</template>

<script>
export default {
  name: 'CitySearch'
}
</script>

<style lang="stylus" scoped>
	@import '~stylePro/varibles.styl'
	.search
		padding:0 .1rem
		height:.72rem
		background:$bgColor
		.search-input
			padding:0 .1rem
			box-sizing:border-box
			width:100%
			heigth:.62rem
			line-height:.62rem
			border-radius:.1rem
			text-align:center
			color:#666
</style>
