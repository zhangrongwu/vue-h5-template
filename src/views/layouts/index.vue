<template>
  <div class="app-container">
    <div class="layout-content">
      <keep-alive :include="whiteList">
        <router-view></router-view>
      </keep-alive>
    </div>
    <div class="layout-footer">
      <TabBar :data="tabbars" @change="handleChange" />
    </div>
  </div>
</template>

<script>
  import TabBar from '@/components/TabBar'
  export default {
    name: 'AppLayout',
    data() {
      return {
        whiteList: ["about", "index"],
        tabbars: [{
            title: '首页',
            to: {
              name: 'Home'
            },
            icon: 'home-o'
          },
          {
            title: '关于我',
            to: {
              name: 'About'
            },
            icon: 'user-o'
          }
        ]
      }
    },
    components: {
      TabBar
    },
    methods: {
      handleChange(v) {
        console.log('tab value:', v)
      }
    }
  }

</script>
