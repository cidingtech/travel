<template>
	<div>
		<CityHeader>City</CityHeader>	
		<CitySearch>Search</CitySearch>
		<CityList :citys="allCitys" :hot="hotCitys" :letter="letter"></CityList>
		<CitySearchTag :citys="allCitys" @change="handleChange"></CitySearchTag>
	</div>
</template>
<script>
import axios from 'axios'
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CitySearchTag from './components/SearchTag'
export default{
	name:'City',
	components:{
		CityHeader,
		CitySearch,
		CityList,
		CitySearchTag
	},
	data(){
		return{
			allCitys:{},
			hotCitys:[],
			letter:''
		}
	},
	methods:{
		getCityInfo(){
			axios.get('/api/city.json').then(this.getSucc)
		},
		getSucc(res){
			console.log(res)
			res = res.data
			if(res.ret && res.data){
				const data = res.data
				this.allCitys = data.cities
				this.hotCitys = data.hotCities
			}
		},
		handleChange(v){
			this.letter = v
		}
	},
	mounted(){
		this.getCityInfo()
	}
}	
</script>
<style lang="stylus" scoped>
	
</style>