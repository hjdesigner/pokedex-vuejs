<template>

</template>

<script>
import axios from "axios";

export default {
  name: "Monster",
  data() {
    return {
      loading: false,
      monster: null,
      errors: [],

      // catched from https://github.com/nolanlawson/pokedex.org/blob/master/src/js/shared/monster/typesToColors.js
      colors: {
        normal: '#A8A878',
        fire: '#F08030',
        fighting: '#C03028',
        water: '#6890F0',
        grass: '#78C850',
        poison: '#A040A0',
        electric: '#F8D030',
        ground: '#E0C068',
        rock: '#B8A038',
        bug: '#A8B820',
        dragon: '#7038F8',
        ghost: '#705898',
        dark: '#705848',
        fairy: '#EE99AC',
        steel: '#B8B8D0',
        psychic: '#F85888',
        ice: '#98D8D8',
        flying: '#A890F0'
      }
    };
  },
  mounted() {
    let vm = this;
  },
  methods: {
  },
  watch: {
    '$route': 'getMonster'
  },
  created() {
    let vm = this;
    // console.log("Monster created");
    vm.getMonster();
  },
  computed: {
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h1,
h2 {
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

.container {
  max-width: 1280px;
  margin: 0 auto;
}

.main-title {
  font-size: 4rem;
  font-weight: 700;
}

.row {
  display: flex;
  .col {
    flex-grow: 1;
    flex-basis: 0;
  }
}

.monster-image {
  width: 500px;
  height: auto;
  display: block;
}

.panel-footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.stats-table {
  border-collapse: collapse;
  width: 100%;

  td, th {
    padding: .5rem 1rem;
    text-align: left;
    border: 1px solid #e7e7e7;
    margin: 0;
  }
  
  th {
    // text-transform: uppercase;
    text-transform: capitalize;
  }
}

.monster-name {
    text-transform: capitalize;
}


.monster-types-list {
  margin: 2rem 0 0;
  padding: 0;
  &__item {
    display: inline-block;
    font-size: 1.2rem;
    padding: .5em;
    border-radius: 5px;
    border: 1px solid #e7e7e7;
    text-transform: capitalize;
    margin: 0;
    span {
      font-weight: 700;
      color: white;
    }
    &:not(:last-child){
      margin-right: 0.25rem;
    }
  }
}

</style>
