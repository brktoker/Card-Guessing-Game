<template>
  <div>
    <div class="card">
      <img :src="card.image" />
    </div>
  </div>
</template>

<script>
export default {
  props: ["card"],
};
</script>
<style scoped>
.card {
  width: 200px;
  height: 232px;
  border-radius: 5px;
  border: 1px solid black;
  transition: box-shadow 0.5s;
  margin-right: 20px;
}
.card:hover {
  box-shadow: 0px 5px 48px #666;
  transition: box-shadow 0.5s;
}
</style>