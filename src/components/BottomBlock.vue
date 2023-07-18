<template>
  <div class="wrapper_block">
    <div class="title">{{ title }}</div>
    <div class="items">
      <ThingItem
        v-for="ThingItem in ThingItems"
        :key="ThingItem"
        :ThingItem="ThingItem"
        @emithItem="
          (data) => {
            this.$emit('emithItem', data);
          }
        "
      ></ThingItem>
    </div>
  </div>
</template>

<script>
import ThingItem from "./ThingItem";
export default {
  name: "BottomBlock",
  components: {
    ThingItem,
  },
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
.wrapper_block {
  border: 2px solid black;
  padding: 10px;
  width: 100%;
}
.title {
  font-size: 24px;
  margin-bottom: 20px;
}
.items {
  display: flex;
  flex-direction: column;
  gap: 5px;
}
</style>
