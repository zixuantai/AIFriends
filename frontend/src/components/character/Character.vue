<script setup>
import {ref} from "vue";

const props = defineProps(['character', 'canEdit'])
const isHover = ref(false)
</script>

<template>
  <div>
    <div class="avatar cursor-pointer">
      <div class="w-60 h-100 rounded-2xl">
        <img :src="character.background_image" class="transition-transform duration-300" :class="{'scale-120': isHover}" alt="">
      </div>
    </div>
    <div>

    </div>
  </div>
</template>

<style scoped>

</style>