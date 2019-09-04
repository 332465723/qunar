<template>
    <div>
       <home-header :city="city"></home-header>
       <home-swiper :swiperList="swiperList"></home-swiper>
       <home-icons :swiperIcons="swiperIcons"></home-icons>
       <home-recommand :recommendList="recommendList"></home-recommand>
       <home-weekend :weekendList="weekendList"></home-weekend>
    </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HomeRecommand from './components/Recommand'
import HomeWeekend from './components/Weekend'
import axios from 'axios'

export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommand,
    HomeWeekend
  },
  data: function () {
    return {
      city: '',
      swiperList: [],
      swiperIcons: [],
      recommendList: [],
      weekendList: []
    }
  },
  methods: {
    getHomeInfo () {
      axios.get('/api/index.json')
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        this.city = res.data.city
        this.swiperList = res.data.swiperList
        this.swiperIcons = res.data.iconList
        this.recommendList = res.data.recommendList
        this.weekendList = res.data.weekendList
      }
    }
  },
  mounted: function () {
    this.getHomeInfo()
  }
}
</script>

<style>
</style>
