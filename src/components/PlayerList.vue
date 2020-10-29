<template>
  <h1>Liste des joueurs {{ playersData.name }}</h1>
  <!-- <div>Ma sélection {{ selection.length }}</div> -->

  <selection-box :selection="selection"></selection-box>
  <!-- <ul>
    <li v-for="(player, index) in playersData.players" :key="index">
      {{ player.name }} ({{ player.number }})
    </li>
  </ul> -->

  <player-card
    v-for="(player, index) in playersData.players"
    :key="index"
    :player="player"
    @add-player="addPlayerToSelection"
  ></player-card>
</template>

<script>
import playersData from "../assets/data/players.json";
import PlayerCard from "./PlayerCard";
import SelectionBox from "./SelectionBox";
export default {
  name: "player-List",
  components: {
    PlayerCard,
    SelectionBox,
  },
  data() {
    return {
      playersData: playersData,
      selection: [],
    };
  },
  methods: {
    addPlayerToSelection(player) {
      this.selection.push(player);
    },
  },
};
</script>
