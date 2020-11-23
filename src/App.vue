<template>
  <component :is="activeComponent"> </component>
</template>
<script>
import GameCards from "./components/GameCards";
import Celebrate from "./components/Celebrate";
import Failure from "./components/Failure";

export default {
  components: {
    appGameCards: GameCards,
    appCelebrate: Celebrate,
    appFailure: Failure,
  },
  data() {
    return {
      activeComponent: "appGameCards",
    };
  },
};
</script>
<style></style>
