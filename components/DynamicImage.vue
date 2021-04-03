<template>
  
    <img :src="dynamicImage">
  
</template>

<script>
export default {
  name: "DynamicImage",

  props: {
    filename: {
      type: String,
      required: true
    }
  },

  computed: {
    dynamicImage() {
      return require(`~/content/ietm/img/${this.filename}`);
    }
  }
};
</script>