<template>
  <div class="wrapper_top_block">
    <div class="title">{{ title }}</div>
    <div class="top_items">
      <ThingItem
        v-for="ThingItem in ThingItems"
        :key="ThingItem"
        :ThingItem="ThingItem"
      ></ThingItem>
    </div>
  </div>
</template>

<script>
import ThingItem from "./ThingItem";

export default {
  name: "TopBlock",
  components: {ThingItem},
  props: {
    title: {
      type: String,
      default() {
        return "";
      },
    },
    ThingItems: {
      type: Array,
      default() {
        return [];
      },
    },
  },
  data() {
    return {};
  },
  mounted() {},
  methods: {},
};
</script>

<style>
.wrapper_top_block{
  border: 2px solid black;
  padding: 10px;
  width: 300px;
  height: 200px;
}
.top_items{
  display: flex;
  gap: 5px;
  flex-wrap: wrap;
}
</style>
