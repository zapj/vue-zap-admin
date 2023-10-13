<template>
  <el-header>
    <el-menu
        class="el-menu-demo"
        mode="horizontal"
        :ellipsis="false"
        @select="handleSelect"
    >
      <el-menu-item index="-1" >
        <span style="width: 10px;text-align: center" ><el-icon><Back></Back></el-icon></span>
      </el-menu-item>
      <el-menu-item index="0">LOGO</el-menu-item>
      <div class="flex-grow" />
      <el-menu-item index="1">Processing Center</el-menu-item>
      <el-sub-menu index="2">
        <template #title>Workspace</template>
        <el-menu-item index="2-1">item one</el-menu-item>
        <el-menu-item index="2-2">item two</el-menu-item>
        <el-menu-item index="2-3">item three</el-menu-item>
        <el-sub-menu index="2-4">
          <template #title>item four</template>
          <el-menu-item index="2-4-1">item one</el-menu-item>
          <el-menu-item index="2-4-2">item two</el-menu-item>
          <el-menu-item index="2-4-3">item three</el-menu-item>
        </el-sub-menu>
      </el-sub-menu>
    </el-menu>




  </el-header>
</template>

<script setup>
import {Back} from "@element-plus/icons-vue";

const handleSelect = (key, keyPath) => {
  console.log(key, keyPath)
  if(key === "-1"){
    emit('closeMenu');
  }
}


const emit = defineEmits(['closeMenu']);

</script>

<style>
.flex-grow {
  flex-grow: 1;
}
</style>
