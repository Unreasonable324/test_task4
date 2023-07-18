<template>
  <div
    class="item"
    @click="
      () => {
        this.$emit('emithItem', ThingItem.id);
      }
    "
  >
    {{ ThingItem.name }}
  </div>
</template>

<script>
export default {
  name: "ThingItem",
  components: {},
  props: {
    ThingItem: {
      type: Object,
      default() {
        return {};
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

<style lang="css" scoped>
.item {
  border: 1px solid black;
  padding: 5px;
  cursor: pointer;
  /* width: 100%; */
  height: 100%;
}
.item:hover {
  background: grey;
}
</style>
