<template>
<section :class="cname">
	<swiper :options="options" :not_next_tick="options.notNextTick">
		<swiper-slide v-for="itenm in items" :key="item.href">
			<router-link :to="{name:''}">
				<img :src="item.src" alt="">
			</router-link>
		</swiper-slide>
		<div class="swiper-pagination" v-if="options.pagination"></div>
	</swiper>
</section>
</template>

<script>

import { swiper, swiperSlide } from 'vue-awesome-swiper'
export default{
	components:{
        swiper,
        swiperSlide
	},
	props:{
        options:{
        	type:Object,
        	default(){
        		return {
        			autoplay:true,
        			loop:true,
        			pagination:{
        				el:".swiper_pagination"
        			},
        			notNextTick:false
        		}
        	}
        },
        items:{
        	type:Array,
        	default(){
        		return []
        	}
        }
	},
	data(){
		return{

		}
	}
}
</script>
<style lang="css">
@import '~swiper/dist/css/swiper.css'	
</style>