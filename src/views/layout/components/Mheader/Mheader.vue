<template>
  <div class="mheader">
    <img src="" alt="">
    <span>B军工作台</span>
    <ul>
      <li>
        <img :src="userLogo" alt="" class="adminLogo">
        <span>Admin</span>
      </li>
      <li>
        <el-badge :value="20" :max="99" class="item">
          <i class="el-icon-bell"></i>
        </el-badge>
      </li>
      <li><i class="el-icon-error"></i></li>
    </ul>
  </div>
</template>

<script>
  import userLogo from '@/assets/img/u225.png'
export default {
  name: 'MheaderItem',
  data() {
    return {
      userLogo
    }
  }
}
</script>

<style rel="stylesheet/scss" lang="scss" scoped>
  @import 'src/styles/mheader.scss';
</style>

