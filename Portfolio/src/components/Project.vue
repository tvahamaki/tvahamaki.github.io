<template>
    <v-sheet v-if="!$vuetify.display.mobile" class="py-4 d-flex align-center">
        <v-img v-if="flip" class="elevation-4" rounded="0" cover aspect-ratio="1.5" width="50%" :src="imageSrc"></v-img>
        <v-sheet>
            <p class="pa-4 text-uppercase text-center text-h5">{{ title }}</p>
            <p class="py-4 px-16 text-justify">{{ text }}</p>
        </v-sheet>
        <v-img v-if="!flip" class="elevation-4" rounded="0" cover aspect-ratio="1.5" width="50%" :src="imageSrc"></v-img>
    </v-sheet>
    <v-sheet v-else>
        <v-img class="mx-auto my-4 elevation-4" rounded="0" cover aspect-ratio="1.5" width="80%" :src="imageSrc"></v-img>
        <p class="pa-4 text-uppercase text-center text-h5">{{ title }}</p>
        <p class="pt-4 pb-16 px-8 text-justify">{{ text }}</p>
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