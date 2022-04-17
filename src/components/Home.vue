<template>
  <Header/>
  <Form/>
</template>

<script>
import Header from './Header.vue'
import Form from "./Form.vue";

export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Home",
  components: {
    Header,
    Form
  }
}
</script>

<style scoped>

</style>