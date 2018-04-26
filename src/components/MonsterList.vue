<template>
</template>
<script>

import axios from 'axios'
export default {
  name: 'MonsterList',
  data () {
    return {
      loading: true,
      totalResults: 0,
      pokemon: [],
      errors: [],
      msg: 'List of Pokemon'
    }
  },
  created () {
    axios.get(`https://pokeapi.co/api/v2/pokemon?limit=151`)
    .then(response => {
      // JSON responses are automatically parsed.
      this.totalResults = response.data.count
      this.pokemon = response.data.results
      this.loading = false;
    })
    .catch(e => {
      this.errors.push(e)
      this.loading = false;
    })
  },
  computed: {
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  h1, h2 {
    font-weight: normal;
  }
  ul {
    list-style-type: none;
    padding: 0;
  }
  li {
    margin: 0 10px;
  }
  a {
    color: #42b983;
  }
</style>
