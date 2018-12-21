<template>
  <div class="counter-warp">
    <text class="title">{{title}}</text>
    <div class='body'>
      <div class="intro flex-raw">
        <text v-for="item in tag" v-bind:key="item.name" class="tag">{{item.name}}</text>
      </div>
      <div v-for="item in contentList" v-bind:key="item.text" class="content">
        <text v-if="item.text" class="text">{{item.text}}</text>
        <image :src='item.image' v-if="item.image" mode='widthFix' class="img"></image>
      </div>
      <div class="related">
<!--         
        <list-view v-for="item in relatedList" v-bind:key="item.title">
          <image src="item.src" class='cover'></image>
          <text style="margin-left:20rpx">{{item.title}}</text>
        </list-view> -->
      </div>
    </div>
  </div>
</template>

<script>
// Use Vuex
import store from './store'

export default {
  data: {
    title: '文章标题',
    contentList: [
      {
        text: 'sdsdsdsdasdasdsazxcxcasdsad',
        image: ''
      },
      {
        text: '',
        image: 'http://www.archcollege.com/wp-content/uploads/2018/12/1544517826288951.jpg'
      },
      {
        text: 'sdsdsdsdasdasdsazxcxcasdsad',
        image: ''
      }
    ],
    tag: [
      {
        name: '标签',
        url: ''
      },
      {
        name: '标签',
        url: ''
      }
    ],
    relatedList: [
      {
        title: '第一篇',
        src: ''
      }
    ]
  },
  computed: {
    count () {
      return store.state.count
    }
  },
  methods: {
    increment () {
      store.commit('increment')
    },
    decrement () {
      store.commit('decrement')
    }
  }
}
</script>

<style>
.title{
  display: flex;
  justify-content: center;
  font-size: 60rpx;
  font-weight: bold;
  color: #333333;
}
.body{
  padding: 60rpx
}
.img{
  width: 100%;
  margin-top: 30rpx;
  margin-bottom: 30rpx;
}
.text{
  color: rgb(48, 48, 48);
  font-size: 40rpx;
}
.intro{
  margin-bottom: 60rpx;
  font-size: 30rpx;
  color:#999;
}
.tag{
  margin: 5rpx;
}
.cover{
  width: 100rpx;
  height: 100rpx;
  border-radius: 5%;
}
</style>
