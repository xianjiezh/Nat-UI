<template>
  <svg class="icon">
    <use :xlink:href="`#i-${iconName}`"></use>
  </svg>
</template>

<script>
export default {
  name: "icon",
  props: ['iconName'],
  created() {
    console.log('this.iconName', this.iconName)
  }
}
</script>

<style lang="scss" scoped>
</style>
