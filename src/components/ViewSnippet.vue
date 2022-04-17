<template>
  <div>
    <ul>
      <li v-for="f in form">
        {{ f }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "ViewSnippet",
  props: ['form']
}
</script>

<style scoped>

</style>