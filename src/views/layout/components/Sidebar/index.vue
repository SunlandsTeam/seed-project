<template>
  <scroll-bar>
    <div :class="['topTitle',isCollapse?'small':'big']">
      <img :src="userLogo" alt="">
      <a href="#/dashboard" v-if="!isCollapse">vue-admin</a>
    </div>
    <el-menu mode="vertical" unique-opened :default-active="$route.path" :collapse="isCollapse" background-color="#304156" text-color="#fff" active-text-color="#409EFF">
      <sidebar-item :routes="routes"></sidebar-item>
    </el-menu>
  </scroll-bar>
</template>

<script>
import { mapGetters } from 'vuex'
import SidebarItem from './SidebarItem'
import ScrollBar from '@/components/ScrollBar'
import userLogo from '@/assets/img/u225.png'

export default {
  data() {
    return {
      userLogo
    }
  },
  components: { SidebarItem, ScrollBar },
  computed: {
    ...mapGetters([
      'sidebar'
    ]),
    routes() {
      return this.$router.options.routes
    },
    isCollapse() {
      return !this.sidebar.opened
    }
  }
}
</script>
<style rel="stylesheet/scss" lang="scss" scoped>
.topTitle{
  height: 50px;
  display: flex;
  align-items: center;
  &.big{
    padding-left: 18px;
  }
  &.small{
    padding-left: 4px;
  }
  a{
    font-weight: bold;
    padding-left: 10px;
    color: white;
    font-size: 18px;
  }
  img{
    width: 25px;
    height: 25px;
    border-radius: 25px;
  }
}
</style>
