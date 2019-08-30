<template>
  <div>
    <div class="recommand-title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <img class="item-img" :src="item.imgUrl" />
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item_desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommand',
  data: function () {
    return {
      recommendList: [
        {
          id: '0001',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1905/e6/e683c8cf5e97ce03a3.img.jpg_200x200_4769276c.jpg',
          title: '世界之窗1',
          desc: '浪漫海洋主题公园，你我的家乡1'
        }, {
          id: '0002',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1905/e6/e683c8cf5e97ce03a3.img.jpg_200x200_4769276c.jpg',
          title: '世界之窗2',
          desc: '浪漫海洋主题公园，你我的家乡2'
        }, {
          id: '0003',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1905/e6/e683c8cf5e97ce03a3.img.jpg_200x200_4769276c.jpg',
          title: '世界之窗3',
          desc: '浪漫海洋主题公园，你我的家乡3'
        }, {
          id: '0004',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1905/e6/e683c8cf5e97ce03a3.img.jpg_200x200_4769276c.jpg',
          title: '世界之窗4',
          desc: '浪漫海洋主题公园，你我的家乡4'
        }, {
          id: '0005',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1905/e6/e683c8cf5e97ce03a3.img.jpg_200x200_4769276c.jpg',
          title: '世界之窗5',
          desc: '浪漫海洋主题公园，你我的家乡5'
        }
      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .recommand-title
    margin-top: .2rem
    line-height: .8rem
    background: #eee
    text-indent: .2rem
  .item
    overflow: hidden
    display: flex
    height: 1.9rem
    .item-img
      width: 1.7rem
      height: 1.7rem
      padding: .1rem
    .item-info
       flex: 1
       padding: .1rem
       min-width: 0
       .item-title
         line-height: .54rem
         font-size: .32rem
         ellipsis()
       .item_desc
         line-height: .4rem
         color: #ccc
         ellipsis()
       .item-button
         line-height: .44rem
         margin-top: .16rem
         background: #ff9300
         padding: 0 .2rem
         border-radius: .06rem
         color: #fff
</style>
