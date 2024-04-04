<template>
    <v-sheet class="py-4 d-flex align-center">
        <v-img v-if="flip" cover aspect-ratio="1.2" width="50%" :src="imageSrc"></v-img>
        <v-sheet>
            <p class="pa-4 text-uppercase text-center text-h5">{{ title }}</p>
            <p class="py-4 px-16 text-center">{{ text }}</p>
        </v-sheet>
        <v-img v-if="!flip" cover aspect-ratio="1.2" width="50%" :src="imageSrc"></v-img>
    </v-sheet>
</template>

<script>
export default {
  props: {
    image: String,
    title: String,
    text: String,
    flip: Boolean
  },
  computed: {
    imageSrc() {
        return new URL(`../assets/${this.image}`, import.meta.url).href
    }
  }
}
</script>