<template>
  <div class="container">
    <div class="row">
      <div class="col-sm-10 mx-auto">
        <form @submit.prevent="postData">
          <div class="form-group">
            <label for="url">URL Новостной ленты</label>
            <input type="url" class="form-control" name="url" id="url" aria-describedby="emailHelp"
                   placeholder="Enter URL">
          </div>
          <div class="form-group">
            <label for="file">Файл</label>
            <input type="file" class="form-control-file" name="file" id="file" @change="processFile($event)">
          </div>
          <button type="submit" class="btn btn-primary mb-3">Submit</button>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
import {createApp} from 'vue'
import axios from 'axios'
import VueAxios from 'vue-axios'
import App from '/src/App.vue'

const app = createApp(App)
app.use(VueAxios, axios)
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Form',
  data() {
    return {
      form: {
        url: null,
        file: []
      }
    }
  },
  methods: {
    async postData() {
      try {
        const res = await fetch('http://127.0.0.1:8000/snippet/create', {
          method: 'POST',
          headers: {
            'Content-Type': 'application/json'
          },
          credentials: 'include',
          body: JSON.stringify({
            url: this.form.url,
            file: this.form.file
          })
        })
        // eslint-disable-next-line no-unused-vars
        const data = await res.json()
        if (res.status === 200) {
          console.log(data)
        } else {
          this.errors = data
          console.log(data)
        }
      } catch (e) {
        console.error(e)
      }
    },
    processFile(e) {
      this.someData = e.target.files[0]
    }
  }
};
</script>

<style scoped>

</style>

<style>
.container {
  margin-top: 40px;
}
</style>