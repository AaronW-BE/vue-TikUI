<template>
  <div class="btn-group">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'ButtonGroup',
  data() {
    return {}
  }
}
</script>

<style scoped>
  .btn-group {
    padding: 5px;
  }
  .btn-group slot {
    margin: 9px;
  }
</style>
