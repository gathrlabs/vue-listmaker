<template>
  <div class='conatiner'>
    <div class="field">
      <label class="label"></label>
      <p class="control">
        <textarea class="textarea is-hovered" @keyup.enter.prevent="createNew" placeholder="Add your quote here" v-model="quote"></textarea>
      </p>
    </div>
    <div class="field is-grouped">
      <p class="control">
        <button class="button is-primary" @click.prevent="createNew">Submit</button>
      </p>
      <p class="control">
        <button class="button is-link" @click="quote=''">Cancel</button>
      </p>
    </div>
  </div>
</template>

<script>
  export default {
    props: ['quoteCount'],
    data: function() {
      return {
        quote: null
      }
    },
    methods: {
      createNew() {
        if(this.quote && this.quoteCount < 10) {
          this.$emit('quoteAdded', this.quote);
          this.quote = null;
        } else {
          console.log('Add a quote')
        }
      }
    }
  }

</script>

<style>

</style>
