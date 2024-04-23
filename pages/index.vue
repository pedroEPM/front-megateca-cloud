<template>

  <cCardVue />
  <cCardVue />
  <cCardVue />
  <cCardVue />
  <cCardVue />
  <cCardVue />

</template>


<script>
import cCardVue from '~/components/cCard.vue';

  export default {
    components: {
      cCardVue
    },
    data () {
      return {
        dialog: false,
        config: useRuntimeConfig(),

      }
    },
  };
</script>


<style>
</style>