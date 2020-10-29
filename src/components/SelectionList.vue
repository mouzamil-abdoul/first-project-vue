<template>
  <h1>Ma sélection</h1>
  <p>Vous n'avez pas sélectionné de joueurs</p>
  {{ selection }}
</template>

<script>
export default {
  name: "selection-list",
  props: ["selection"],
};
</script>

<style></style>
