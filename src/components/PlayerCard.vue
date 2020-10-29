<template>
  <div class="border border-red-900 m-2 p-2 rounded " :class="isInjuredClass">
    <h3 class="text-lg font-bold">{{ playerName }} ({{ player.number }})</h3>
    <p>{{ player.position }}</p>
    <base-button text="Sélectionner" @click="addToSelection"></base-button>
  </div>
</template>

<script>
export default {
  name: "player-card",
  props: ["player"],

  computed: {
    playerName() {
      if (this.player.name.split(".").length > 1) {
        return this.player.name.split(".")[1];
      }
      return this.player.name;
    },

    playerInjured() {
      if (this.player.health == "out") {
        return true;
      }
      return false;
    },
    isInjuredClass() {
      return {
        "bg-red-500": this.playerInjured,
        "bg-green-300": !this.playerInjured,
      };
    },
  },
  methods: {
    addToSelection() {
      this.$emit("add-player", this.player);
    },
  },
};
</script>

<style></style>
