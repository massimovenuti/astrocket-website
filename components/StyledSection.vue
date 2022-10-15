<template>
  <div class="styled-section">
    <h2 class="styled-section-title">
      {{ title }}
    </h2>
    <p class="styled-section-description">
      {{ description }}
    </p>
  </div>
</template>

<script>
export default {
  name: "StyledSection",
  props: {
    title: {
      type: String,
      required: true
    },
    description: {
      type: String,
      required: true
    }
  }
}
</script>

<style>
.styled-section{
  @apply divide-y divide-gray-300;
}

.styled-section-title{
  @apply text-lg font-semibold capitalize p-2 text-left;
}

.styled-section-description{
  @apply p-2;
}
</style>
