<template>
  <ul>
    <li 
      v-for="color in colors" 
      :key="color"
      @click="$emit('click', color)"
    >{{color}}</li>
  </ul>
</template>

<script>
export default {
  props: ['match'],

  computed: {
    colors() {
      return this.$store.getters.pickColor(this.match)
    }
  }
}
</script>

<style scoped lang="scss">
ul{
  position: absolute;
}
li:hover {
  cursor: grab;
}
</style>