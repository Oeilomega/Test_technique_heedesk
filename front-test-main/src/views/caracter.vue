<template>
  <div class="caracter">
      {{"Nom : " + name + ','}}
      {{"Poids : " + weight + ','}}
      {{"Couleur des yeux : " + eye_color}}
  </div>
</template>

<script>

export default {
  name: 'caracter',
  props: {
      name: String,
      weight: Number,
      eye_color: String,
  }
}
</script>