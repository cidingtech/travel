<template>
  <ul class="list">
  	<li class="item" 
  	v-for="item of letters" 
  	:key="item" 
  	:ref="item"
  	@click="handleClick" 
  	@touchstart="touchStart"
  	@touchmove="touchMove"
  	@touchend="touchEnd">{{item}}</li>
  </ul>
</template>

<script>
export default {
  name: 'CitySearchTag',
  props:{
  	citys:Object
  },
  computed:{
  	letters(){
  		const letters=[]
  		for (let i in this.citys) {
  			letters.push(i)
  		}
  		return letters
  	}
  },
  data(){
  	return{
  		touchStatus:false,
  		startY:0,
  		timer:null
  	}
  },
  updated(){
  	this.startY=this.$refs['A'][0].offsetTop
  },
  methods:{
  	handleClick(e){
  		this.$emit('change',e.target.innerText)
  	},
  	touchStart(){
  		this.touchStatus = true
  	},
  	touchMove(e){
  		if(this.touchStatus){
  			if(this.timer){
  				clearTimeout(this.timer)
  			}
  			this.timer = setTimeout(()=>{
	  			const y = this.startY
	  			const touchY = e.touches[0].clientY - 79
	  			const idx = Math.floor((touchY-y)/20)
	  			if(idx>=0 && idx<this.letters.length){
	  				this.$emit('change',this.letters[idx])
	  			}
  			},16)
  		}
  	},
  	touchEnd(){
  		this.touchStatus = false
  	}
  }
}
</script>

<style lang="stylus" scoped>
	@import '~stylePro/varibles.styl'
	.list
		display:flex
		flex-direction:column
		justify-content:center
		position:absolute
		top:1.58rem
		right:0
		bottom:0
		width:.4rem
		.item
			text-align:center
			line-height:.4rem
			color:$bgColor
</style>
