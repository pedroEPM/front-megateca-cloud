<template>
    <v-layout row wrap>
        <v-row>
            <v-flex v-for="i in [1,2,3,4]" :key="i"   class="pa-5 xs12 md4" >
                <cCardVue />        
            </v-flex>
        </v-row>
    </v-layout>
</template>

<script>
import cCardVue from "~/components/cCard.vue";

export default {
  components: {
    cCardVue,
  },
};
</script>

<style>
</style>