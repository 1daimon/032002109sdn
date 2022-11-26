<template>
  <div class="page">
    <img  class="back_ima" src="https://pic.imgdb.cn/item/6380b89316f2c2beb1f9e183.jpg" alt="拓扑视图">
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
.back_ima{
    width:100%;
    height: 100%;
    position: absolute;
    z-index: -1;
}
.page{
    width:100%;
   position: relative;
    display: flex;
    flex-wrap: wrap;
    min-height: 100vh;
}
</style>