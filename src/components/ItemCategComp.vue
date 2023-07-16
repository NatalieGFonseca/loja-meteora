<template>
    <div class="categories">
        <div class="information">
        <img :src="imgSrc" :alt="textSrc" >
            <h3 class="label">{{ textSrc }}</h3>
        </div>
    </div>
</template>

<script setup>

defineProps({
    imgSrc: {
    type: String,
    required: true
  },
  textSrc: {
    type: String,
    required: true
  },
})
</script>