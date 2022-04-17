<template>
  <div class="nav">
    <a href="#">SGen</a>
    <a href="#">Generation Snippet</a>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Header'
}
</script>

<style scoped>

</style>

<style>
.nav {
  background-color: #333;
  overflow: hidden;
}
.nav a{
  float: left;
  color: #f2f2f2f2;
  padding: 14px 16px;
  text-align: center;
  font-size: 17px;
  text-decoration: none;
  margin-right: 5px;
}
.nav a:hover {
  background: #ddd;
  color: #333;
}
</style>