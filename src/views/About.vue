<template>
  <div class="container">
    <div class="row">
      <div class="col-3">
        <h3>JUNE 4</h3>
        <draggable class="list-group" :list="list1" group="people" @change="log">
          <div class="list-group-item" v-for="element in list1" :key="element.name">
            {{ element.name }}
          </div>
        </draggable>
      </div>

      <div class="col-3">
        <h3>JUNE 5</h3>
        <draggable class="list-group" :list="list2" group="people" @change="log">
          <div class="list-group-item" v-for="element in list2" :key="element.name">
            {{ element.name }}
          </div>
        </draggable>
      </div>

      <!-- <rawDisplayer class="col-3" :value="list1" title="List 1" /> -->

      <!-- <rawDisplayer class="col-3" :value="list2" title="List 2" /> -->
    </div>

    <div class="row">
      <draggable class="col-6" :box="box1" group="people" @change="log">
        <div class="box-item"><h1>BOX</h1></div>
      </draggable>
      <draggable class="col-6" :box="box2" group="people" @change="log">
        <div class="box-item"><h1>BOX</h1></div>
      </draggable>
    </div>

    <!-- <div class="inside-row">
      <div class="col-3">
        <h3>PEOPLE</h3>
        <draggable class="list-group" :list="list1" group="people" @change="log">
          <div class="list-group-item" v-for="element in list1" :key="element.name">
            {{ element.name }}
          </div>
        </draggable>
      </div> -->

    <!-- <div class="col-3">
      <h3>OTHER</h3>
      <draggable class="list-group" :list="list2" group="people" @change="log">
        <div class="list-group-item" v-for="element in list2" :key="element.name">
          {{ element.name }}
        </div>
      </draggable>
    </div> -->

    <!-- <rawDisplayer class="col-3" :value="list1" title="List 1" /> -->

    <!-- <rawDisplayer class="col-3" :value="list2" title="List 2" /> -->
    <!-- </div> -->

    <div class="row">
      <draggable class="col-6" :box="box1" group="people" @change="log">
        <h3>JUNE 4</h3>
        <div class="box-item">
          <div class="col-3">
            <draggable class="list-group" :list="list1" group="people" @change="log">
              <div class="list-group-item" v-for="element in list1" :key="element.name">
                {{ element.name }}
              </div>
            </draggable>
          </div>
        </div>
      </draggable>
      <draggable class="col-6" :box="box2" group="people" @change="log">
        <h3>JUNE 5</h3>
        <div class="box-item">
          <div class="col-3">
            <draggable class="list-group" :list="list2" group="people" @change="log">
              <div class="list-group-item" v-for="element in list2" :key="element.name">
                {{ element.name }}
              </div>
            </draggable>
          </div>
        </div>
      </draggable>
    </div>

    <div class="slider">
      <h1>Your Trip Calendar</h1>
      <div class="full hide-scroll">
        <ul class="hs">
          <li class="item">
            <draggable class="col-6" :box="box1" group="people" @change="log">
              <h3>JUNE 4</h3>
              <div class="box-item">
                <div class="col-3">
                  <draggable class="list-group" :list="list1" group="people" @change="log">
                    <div class="list-group-item" v-for="element in list1" :key="element.name">
                      {{ element.name }}
                    </div>
                  </draggable>
                </div>
              </div>
            </draggable>
          </li>
          <li class="item">
            <draggable class="col-6" :box="box2" group="people" @change="log">
              <h3>JUNE 5</h3>
              <div class="box-item">
                <div class="col-3">
                  <draggable class="list-group" :list="list2" group="people" @change="log">
                    <div class="list-group-item" v-for="element in list2" :key="element.name">
                      {{ element.name }}
                    </div>
                  </draggable>
                </div>
              </div>
            </draggable>
          </li>
          <li class="item">June 6</li>
          <li class="item">June 7</li>
          <li class="item">June 8</li>
          <li class="item">June 9</li>
        </ul>
      </div>
    </div>
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
      box1: { name: "BOX1", id: 1 },
      box2: { name: "BOX2", id: 2 },
      box3: { name: "BOX3", id: 3 },
      box4: { name: "BOX4", id: 4 },
      box5: { name: "BOX5", id: 5 },
      box6: { name: "BOX6", id: 6 },
      list1: [
        { name: "HILO FARMERS MARKET", id: 1 },
        { name: "AKAKA FALLS", id: 2 },
        { name: "CARLSMITH BEACH PARK", id: 3 },
        { name: "DINNER AT PINEAPPLES", id: 4 },
      ],
      list2: [
        { name: "KAHENA BEACH", id: 5 },
        { name: "VOLCANO NATIONAL PARK", id: 6 },
        { name: "VOLCANO WINERY", id: 7 },
      ],
    };
  },
  methods: {
    // add: function () {
    //   this.list.push({ name: "BOX1" });
    // },
    // replace: function () {
    //   this.list = [{ name: "BOX2" }];
    // },
    // clone: function (el) {
    //   return {
    //     name: el.name + " cloned",
    //   };
    // },
    // log: function (evt) {
    //   window.console.log(evt);
    // },
    // add2: function () {
    //   this.box.push({ name: "DINOSAURS" });
    // },
    // replace2: function () {
    //   this.box = [{ name: "KITTENS" }];
    // },
    // clone2: function (el) {
    //   return {
    //     name: el.name + " cloned",
    //   };
    // },
    // log2: function (evt) {
    //   window.console.log(evt);
    // },
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
  margin: 5px;
  padding: 8px;
  background-color: #fff;
}
.list-group-item {
  border: 1px solid black;
  border-radius: 10px;
  background: gray;
  margin: 2px;
  padding: 5px;
  min-width: 200px;
  color: white;
  text-shadow: 1px 1px 3px black;
}

.col-6 {
  border: 1px solid black;
  margin: 5px;
  border-radius: 10px;
  padding: 8px;
  background-color: gray;
  min-height: 300px;
}

.box-item {
  border: 1px solid black;
  border-radius: 10px;
  background: #fff;
  margin: 2px;
  padding: 5px;
  min-width: 200px;
}

h3 {
  color: white;
  text-shadow: 1px 1px 3px black;
}
:root {
  --gutter: 20px;
}

.slider {
  padding: var(--gutter) 0;
  display: grid;
  grid-gap: var(--gutter) 0;
  grid-template-columns: var(--gutter) 1fr var(--gutter);
  align-content: start;
}

.slider > * {
  grid-column: 2 / -2;
}

.slider > .full {
  grid-column: 1 / -1;
}

.hs {
  display: grid;
  grid-gap: calc(var(--gutter) / 2);
  grid-template-columns: 10px repeat(6, calc(50% - var(--gutter) * 2)) 10px;
  grid-template-rows: minmax(300px, 1fr);

  overflow-x: scroll;
  scroll-snap-type: x proximity;
  padding-bottom: calc(0.75 * var(--gutter));
  margin-bottom: calc(-0.5 * var(--gutter));
  min-height: 340px;
}

.hs:before,
.hs:after {
  content: "";
}

/* Hide scrollbar */
.hide-scroll {
  overflow-y: hidden;
  margin-bottom: calc(-0.1 * var(--gutter));
}

.slider {
  width: auto;
  height: auto;
  background: #dbd0bc;
  overflow-y: scroll;
  margin-left: 10%;
  margin-right: 10%;
}

.hs > li,
.item {
  scroll-snap-align: center;
  padding: calc(var(--gutter) / 2 * 1.5);
  display: flex;
  flex-direction: column;
  justify-content: start;
  align-items: center;
  background: #fff;
  border-radius: 8px;
  height: 270px;
}

router-link {
  text-decoration: none;
}
</style>
