<template>
    <div class="facilities">
        <div class="information">
            <img  :src="imgSrc" :alt="textSrc" />
            <div class="block">
                <h3 class="label">{{ textSrc }}</h3>
                <p class="description">{{ description }}</p>
            </div>
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
  description: {
    type: String,
    required: true
  }
})
</script>