<template>
  <div class="columns is-multiline is-mobile">
    <app-quote v-for="(quote, index) in quotes">
      <div class="column">
        <div class="box">
          <div class="quote-text">
            {{ quote }}
          </div>
          <a @click="removeQuote(index)" class="delete"></a>
        </div>
      </div>
    </app-quote>
  </div>
</template>

<script>
  import Quote from './Quote.vue'

  export default {
    props: ['quotes'],
    components: {
      'app-quote': Quote
    },
    methods: {
      removeQuote(index) {
        this.$emit('removeQuote', index)
      }
    }
  }
</script>

<style lang="css" scoped>
  .columns {
    margin-top: 50px;
  }
  .box {
    box-shadow:0px 1.5px 4px rgba(0, 0, 0, 0.12);
    transition: box-shadow 0.4s;
    cursor: pointer;
    position: relative;
  }

   .box:hover {
    color:LightSlateGray;
    box-shadow: 0 10px 20px rgba(0, 0, 0, 0.22), 0 14px 56px rgba(0, 0, 0, 0.25);
  }

  .box .delete {
    position: absolute;
    right: 0.5em;
    top: 0.5em;
  }

  .quote-text {
    margin: 20px;
  }
</style>
