<script setup>
import LeftSidebar from "@/components/LeftSidebar.vue";
import TopMenu from "@/components/TopMenu.vue";
import {ref,onMounted} from "vue";
onMounted(()=>{

})
const leftSidebar = ref()
const closeMenu = ()=>{
  console.log('closeMenu')
  leftSidebar.value.closeMenu()
}
</script>

<template>
    <el-container>
      <LeftSidebar ref="leftSidebar" @closeMenu="closeMenu"></LeftSidebar>
      <el-container>
          <TopMenu></TopMenu>
        <el-main>
          <RouterView></RouterView>
        </el-main>
        <el-footer>Footer</el-footer>
      </el-container>
    </el-container>
    <el-backtop :right="10" :bottom="100" />
</template>

<style scoped>

</style>
