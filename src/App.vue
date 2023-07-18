<template>
  <div class="wrapper">
    <div class="top">
      <TopBlock :title="'Выбранные вещи'" :ThingItems="TopLeft"></TopBlock>
      <TopBlock :title="'Выбранная вещь'" :ThingItems="TopRight"></TopBlock>
    </div>
    <div class="bottom">
      <BottomBlock
        :title="'Bещи у пользователя'"
        :ThingItems="LeftBlock"
        @emithItem="selectedItems"
      ></BottomBlock>
      <BottomBlock
        :title="'Bвещи на выбор'"
        :ThingItems="RightBlock"
        @emithItem="selectedItem"
      ></BottomBlock>
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
      TopLeft: [],
      TopRight: [],
      LeftBlock: [
        {
          id: 1,
          name: "Shoes 1",
        },
        {
          id: 2,
          name: "Shoes 2",
        },
        {
          id: 3,
          name: "Shoes 3",
        },
        {
          id: 4,
          name: "Shoes 4",
        },
        {
          id: 5,
          name: "T-shirt 1",
        },
        {
          id: 6,
          name: "T-shirt 2",
        },
        {
          id: 7,
          name: "T-shirt 3",
        },
        {
          id: 8,
          name: "T-shirt 4",
        },
      ],
      RightBlock: [
        {
          id: 11,
          name: "Jacket 1",
        },
        {
          id: 12,
          name: "Jacket 2",
        },
        {
          id: 13,
          name: "Jacket 3",
        },
        {
          id: 14,
          name: "Jacket 4",
        },
        {
          id: 15,
          name: "Hoodie 1",
        },
        {
          id: 16,
          name: "Hoodie 2",
        },
        {
          id: 17,
          name: "Hoodie 3",
        },
        {
          id: 18,
          name: "Hoodie 4",
        },
      ],
    };
  },
  components: {
    BottomBlock,
    TopBlock,
  },
  methods: {
    selectedItems(data) {
      if (this.TopLeft.find((x) => x.id === data)) {
        let index = this.TopLeft.map((x) => {
          return x.id;
        }).indexOf(data);

        this.TopLeft.splice(index, 1);
      } else if (this.TopLeft.length < 6) {
        this.TopLeft.push(this.LeftBlock.find((x) => x.id === data));
      }
    },
    selectedItem(data) {
      this.TopRight = [];
      this.TopRight.push(this.RightBlock.find((x) => x.id === data));
    },
  },
};
</script>

<style scoped>
.wrapper {
  padding: 20px;
  display: flex;
  flex-direction: column;
  gap: 25px;
}

.top,
.bottom {
  display: flex;
  justify-content: space-between;
  gap: 20px;
}
</style>
