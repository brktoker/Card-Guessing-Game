<template>
  <div>
    <div class="card">
    </div>
  </div>
</template>

<script>
export default {
    
}
</script>
<style scoped>
.card {
  width: 200px;
  height: 232px;
  border-radius: 5px;
  border: 1px solid black;
  transition: box-shadow 0.5s;
  margin-right: 20px;
  background-image: url("../assets/cute-angel-cat.jpg");
  background-size: cover;
  box-shadow: 0px 5px 48px #666;
}
.card:hover {
  box-shadow: 0px 5px 48px black;
  transition: box-shadow 0.5s;
}
</style>