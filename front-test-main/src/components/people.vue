<template>
  <div>
    <div v-for="(character_name, name) of characters_list" :key="name">
     <router-link :to="{name: 'Caracter', params:  { name: character_name.name, weight: character_name.mass, eye_color: character_name.eye_color }}">{{character_name.name}}</router-link>
    </div>
  </div>
</template>

<script>

export default {
  name: 'People',
  props: {
      characters_list: Array
  }
}
</script>
