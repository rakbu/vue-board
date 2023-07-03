<template>
  <section>
    <h1>{{ boardName }}</h1>
    <div class="board">
      <div class="board__columns" v-for="item in columns" :key="item.id">
        <div class="board__columns__header">
          {{ item.name }}
        </div>
        <draggable
          v-model="item.data"
          group="board"
          handle=".handle"
          class="board__columns__draggable_area"
          :key="item.data.id"
        >
          <div
            class="handle"
            v-for="chartItem in item.data"
            :key="chartItem.id"
          >
            <div v-if="chartItem.id" @click="openModal(item)">
              <Chart
                :chartData="chartItem"
                :chartArray="item.data"
                :chartClass="'handle'"
              ></Chart>
            </div>
          </div>
        </draggable>
      </div>
    </div>
  </section>
</template>
<script>
import Chart from "@/components/chart/ChartColumns.vue";
import draggable from "vuedraggable";

export default {
  name: "Scene",
  components: {
    Chart,
    draggable,
  },
  data() {
    return {
      boardName: "Agile Board",
      columns: [
        {
          id: 0,
          name: "Backlog",
          isEnd: false,
          data: [
            {
              id: 1234,
              name: "Slider wont work",
              points: 3,
              assigne: "User Id",
              sprint: "Sprint 1",
            },
          ],
        },
        {
          id: 1,
          name: "To / Do",
          isEnd: false,
          data: [
            {
              id: 12354,
              name: "Slider working",
              points: 6,
              assigne: "User Id",
              sprint: "Sprint 1",
            },
          ],
        },
        { id: 2, name: "In Progress", isEnd: false, data: [{}] },
        { id: 3, name: "Test", isEnd: false, data: [{}] },
        { id: 4, name: "Ready to release", isEnd: false, data: [{}] },
        { id: 5, name: "Live", isEnd: false, data: [{}] },
        { id: 6, name: "Done", isEnd: true, data: [{}] },
      ],
      list: [],
    };
  },
  methods: {
    openModal(item){
      console.log("modal opened: ", item)
    },
  },
};
</script>

<style lang="scss" scoped>
.board {
  display: flex;
  height: 90vh;
  gap: 15px;
  &__columns {
    max-width: 300px;
    width: 100%;
    border: 1px solid #ccc;
    border-radius: 7px;
    background: #b1adad;
    &__header {
      width: 100%;
      display: flex;
      align-items: center;
      justify-content: center;
      text-align: center;
      font-size: 18px;
      padding: 10px 0px;
      background: #ccc;
    }
    &__draggable_area {
      height: 100vh;
      display: flex;
      flex-direction: column;
    }
  }
}
</style>
