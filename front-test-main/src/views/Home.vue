<template>
  <div class="home">
    <Search :search_keyword='search' v-on:startsearch="start_search"/>
    <People :characters_list='characters.results'/>
  </div>
</template>

<script>
import People from '../components/people.vue'
import Search from '../components/search.vue'
import axios from 'axios';

export default {
  name: 'Home',
  components: { People, Search },
  data() {
    return {
      characters: [],
      search: ""
    }
  },
  methods: {
    start_search(newSearch) {
      this.search = newSearch;
      console.log(this.search)
      axios.get(`https://swapi.dev/api/people/?search=` + this.search)
      .then(response => {
        this.characters = response.data
      })
      .catch({})
    }
  },

  created() {
    axios.get(`https://swapi.dev/api/people/`)
    .then(response => {
      this.characters = response.data
    })
    .catch({})
  }
}
</script>
