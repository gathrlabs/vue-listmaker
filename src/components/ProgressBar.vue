<template>
  <progress class="progress is-info" :value="quoteCount" max="10"></progress>
</template>

<script>
export default {
  props: ['quoteCount'],
  data: function() {
    return {

    }
  }
}
</script>

<style>

</style>
