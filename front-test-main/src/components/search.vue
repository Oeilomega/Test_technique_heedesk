<template>
  <div>
    <div class="col-l-4">
        <div class="form-input-set" style="background: white">
            <input v-bind:value="search_keyword" v-on:input="$emit('startsearch', $event.target.value)" class="form-input">
        </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Search',
  props: {
      search_keyword: String,
  },
  data () {
      return {

      }
    },
}
</script>
