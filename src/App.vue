<template>
  <nav-bar @change-component="updateSelectedComponent"></nav-bar>
  <keep-alive>
    <component :is="selectedComponent" v-bind="currentProps"></component>
  </keep-alive>
</template>

<script>
import PlayerList from "./components/PlayerList.vue";
import SelectionList from "./components/SelectionList";
import NavBar from "./components/navigation/NavBar";
export default {
  name: "App",
  components: {
    PlayerList,
    SelectionList,
    NavBar,
  },
  data() {
    return { selectedComponent: "player-list" };
  },
  computed: {
    currentProps() {
      if (this.selectedComponent == "selection-list") {
        return { selection: this.selectedComponent };
      }
      return false;
    },
  },
  methods: {
    updateSelectedComponent(comp) {
      this.selectedComponent = comp;
    },
  },
};
</script>

<style>
/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
</style>
