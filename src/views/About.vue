<template>
  <div class="row">
    <div class="col-3">
      <h3>PEOPLE</h3>
      <draggable class="list-group" :list="list1" group="people" @change="log">
        <div class="list-group-item" v-for="element in list1" :key="element.name">
          {{ element.name }}
        </div>
      </draggable>
    </div>

    <div class="col-3">
      <h3>OTHER</h3>
      <draggable class="list-group" :list="list2" group="people" @change="log">
        <div class="list-group-item" v-for="element in list2" :key="element.name">
          {{ element.name }}
        </div>
      </draggable>
    </div>

    <rawDisplayer class="col-3" :value="list1" title="List 1" />

    <rawDisplayer class="col-3" :value="list2" title="List 2" />
  </div>
</template>
<script>
import draggable from "vuedraggable";
export default {
  name: "two-lists",
  display: "Two Lists",
  order: 1,
  components: {
    draggable,
  },
  data() {
    return {
      list1: [
        { name: "John", id: 1 },
        { name: "Joao", id: 2 },
        { name: "Jean", id: 3 },
        { name: "Gerard", id: 4 },
      ],
      list2: [
        { name: "DINOSAURS", id: 5 },
        { name: "KITTENS", id: 6 },
        { name: "FIELD MOUSE", id: 7 },
      ],
    };
  },
  methods: {
    add: function () {
      this.list.push({ name: "DINOSAURS" });
    },
    replace: function () {
      this.list = [{ name: "KITTENS" }];
    },
    clone: function (el) {
      return {
        name: el.name + " cloned",
      };
    },
    log: function (evt) {
      window.console.log(evt);
    },
  },
};
</script>
<style>
.row {
  display: flex;
  background-color: beige;
  padding: 10px;
  border: 1px solid black;
  border-radius: 10px;
  justify-content: center;
}

.list-group {
  border: 1px solid black;
  margin: 5px;
  border-radius: 10px;
  padding: 8px;
  background-color: gray;
}
.list-group-item {
  border: 1px solid black;
  background: #fff;
  margin: 2px;
  padding: 5px;
  min-width: 200px;
}
</style>
