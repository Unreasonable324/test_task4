<template>
  <div class="wrapper">
    <div class="top">
      <TopBlock></TopBlock>
      <TopBlock></TopBlock>
    </div>
    <div class="bottom">
      <BottomBlock></BottomBlock>
      <BottomBlock></BottomBlock>
    </div>
  </div>
</template>

<script>
import BottomBlock from "./components/BottomBlock";
import TopBlock from "./components/TopBlock";
export default {
  name: "App",
  data() {
    return {
      
    }
  },
  components: {
    BottomBlock,
    TopBlock,
  },
};
</script>

<style>
.wrapper{
  padding: 20px;
  display: flex;
  flex-direction: column;
  gap: 25px;
}
.top, .bottom{
  display: flex;
  justify-content: space-between;
}
</style>
