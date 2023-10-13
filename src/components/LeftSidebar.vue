<template>
  <el-aside width="auto" >
  <div class="row" style="height: 50px;line-height: 50px;text-align: center;color: #44d944;font-weight: bold">
    <el-icon><icon-menu /></el-icon>
    <span class="hidden-sm-and-down " ref="logoname">ZAP AdminUI</span>
  </div>
    <el-menu
        active-text-color="#44D944FF"
        background-color="#363636"
        class="el-menu-vertical-demo"
        text-color="#fff"
        @open="handleOpen"
        @close="handleClose"
        :collapse="leftMenuRef"
    >
      <el-menu-item index="0">
        <el-icon><icon-menu /></el-icon>
        <span>ZAP AdminUI</span>
      </el-menu-item>
      <el-sub-menu index="1">
        <template #title>
          <el-icon><location /></el-icon>
          <span>Navigator One</span>
        </template>
        <el-menu-item-group title="Group One">
          <el-menu-item index="1-1">item one</el-menu-item>
          <el-menu-item index="1-2">item two</el-menu-item>
        </el-menu-item-group>
        <el-menu-item-group title="Group Two">
          <el-menu-item index="1-3">item three</el-menu-item>
        </el-menu-item-group>
        <el-sub-menu index="1-4">
          <template #title>item four</template>
          <el-menu-item index="1-4-1">item one</el-menu-item>
        </el-sub-menu>
      </el-sub-menu>
      <el-menu-item index="2">
        <el-icon><icon-menu /></el-icon>
        <span>Navigator Two</span>
      </el-menu-item>
      <el-menu-item index="3" disabled>
        <el-icon><document /></el-icon>
        <span>Navigator Three</span>
      </el-menu-item>
      <el-menu-item index="4">
        <el-icon><setting /></el-icon>
        <span>Navigator Four</span>
      </el-menu-item>
    </el-menu>
  </el-aside>
</template>

<script setup>
import {
  Document,
  Menu as IconMenu,
  Location,
  Setting,
} from '@element-plus/icons-vue'
import {ref} from "vue";

const leftMenuRef = ref(false);
const logoname = ref();
const handleOpen = (key, keyPath) => {
  console.log(key, keyPath)
}
const handleClose = (key,keyPath) => {
  console.log(key, keyPath)
}

const closeMenu = ()=> {
  console.log(leftMenuRef.value)
  // logoname.value.style.display = logoname.value.style.display === 'none' ? 'inline-block' : 'none';
  leftMenuRef.value = !leftMenuRef.value;

  console.log("closeMenu left")
}


defineExpose({
  closeMenu
})

</script>
