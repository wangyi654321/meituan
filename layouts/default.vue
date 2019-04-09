<template>
  <div>
    <el-container class="layout-default">
      <el-header style="height:197px">
        <my-header></my-header>
      </el-header>
      <el-main> 
        <nuxt />
      </el-main>
      <el-footer height="100%">
        <my-footer></my-footer>
      </el-footer>
    </el-container>
  </div>
</template>
<script>
import myHeader from '@/components/public/header/index.vue'
import MyFooter from '@/components/public/footer/index.vue'
export default {
  components:{
    myHeader,
    MyFooter
  }
}
</script>