<template>
  <el-container>

    <el-aside >
      <switch></switch>
      <side-menu></side-menu>
    </el-aside>

    <el-main >
      Main
    </el-main>

  </el-container>
</template>

<script>
    import SideMenu from "./SideMenu";
    export default {
      name: "LibraryIndex",
      components: {SideMenu}
    }
</script>

<style scoped>

</style>
