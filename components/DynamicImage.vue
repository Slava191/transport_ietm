<template>
  <div class="dyn-img">
    <div>
      <img :src="dynamicImage">
    </div>
    <div class="description">
      Рисунок. {{description}}
    </div>
  </div>
</template>

<style scoped>
.dyn-img{
  margin: 20px 0;
}

.description{
  padding: 4px 10px;
  font-weight: bold;
  font-size: 10pt;
}
</style>

<script>
export default {
  name: "DynamicImage",
  props: {
    filename: {
      type: String,
      required: true
    },
    description: {
      type: String,
    }
  },
  computed: {
    dynamicImage() {
      return require(`~/content/ietm/img/${this.filename}`);
    }
  }
};
</script>