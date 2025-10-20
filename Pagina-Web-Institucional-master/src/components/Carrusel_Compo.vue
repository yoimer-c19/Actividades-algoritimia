<template>
  <v-carousel
    height="400"
    show-arrows="hover"
    cycle
    hide-delimiter-background
  >
    <v-carousel-item
      v-for="(slide) in slides" :key="i"
       :src="slide"
        cover
    >
    
    </v-carousel-item>
  </v-carousel>
</template>

<script setup>
  const colors = [
    'indigo',
    'warning',
    'pink darken-2',
    'red lighten-1',
    'deep-purple accent-4',
  ]
  const slides = [
    "https://upload.wikimedia.org/wikipedia/commons/6/63/Reyes_catolicos_colegio_bogota.jpg",
    "https://upload.wikimedia.org/wikipedia/commons/1/12/Colegio_Rosa_de_Santa_Mar%C3%ADa_patio_2017.jpg",
    "https://live.staticflickr.com/7748/17369825872_3968dcee76_b.jpg",
  ]
</script>