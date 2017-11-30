<template>
  <section>
    <ul>
      <li v-for="resposta in respostas">
        <p><strong>{{resposta.title}}</strong></p>
        <p>{{resposta.body}}</p>
      </li>
    </ul>
  </section>
</template>

<script>
import axios from 'axios';

export default {
  name: 'hello',
  data () {
    return {
      respostas: [],
    }
  },
  created() {
    axios.get(`http://jsonplaceholder.typicode.com/posts`)
    .then(response => {
      this.respostas = response.data
    })
  }
}
</script>

<style>
ul {  
  list-style: none;
}
</style>
