<template>
 <p v-if="dialog">Getting data</p>
 <v-container >
    <v-row v-if="pdfs.length > 0">
      <v-col
        v-for="item in pdfs"
        :key="item._id"
        cols="12"
        sm="12"
        md="3"
      >
        <cCardVue 
          :notebook="item.notebook[0]?.NoteBookName ?? 'Sin cuaderno'"
          :publication="item.publication[0]?.publicationName ?? 'Sin publicación'"
          :date="item.datePublication"
          :image="storage + item.newSRCPDFThumbnail"
          :newId="item.isNewId"
        />
      </v-col>
    </v-row>
  </v-container>

</template>


<script>
import cCardVue from '~/components/cCard.vue';

  export default {
    components: {
      cCardVue
    },
    data () {
      return {
        dialog: true,
        api: useRuntimeConfig().public.apiBase,
        storage: useRuntimeConfig().public.storage,

        pdfs: [],
        page: 10,

      }
    },
    methods: {
      async getPDFs() {
        try {
          this.dialog = true;

          const response = await $fetch(`${this.api}/pdfs?page=${this.page}`, {
            method: 'GET',
          });
          this.pdfs = await response?.msg;
          this.dialog = false;
          
        } catch (error) {
          console.log('Error ', error)
        }
      }
    },
    mounted() {
      this.getPDFs()
    }
  };
</script>


<style>
</style>