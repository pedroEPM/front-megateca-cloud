<template>
  <section v-if="pdf !== null">
    <img :src="storage + pdf.newSRCPDF" :alt="pdf.title" loading="lazy" />
  </section>
  <section v-else>
    <h2>PDF NO ENCONTRADO</h2>
  </section>
</template>

<script>
export default {
  data() {
    return {
      dialog: true,
      api: useRuntimeConfig().public.apiBase,
      storage: useRuntimeConfig().public.storage,

      id: null,
      pdf: null,
    };
  },
  created() {
    if (this.$route?.query?.id) this.id = this.$route?.query?.id;
    if (this.id) this.getPDF();
  },
  methods: {
    async getPDF() {
      try {
        this.dialog = true;

        const response = await $fetch(`${this.api}/pdfs/${this.id}`, {
          method: "GET",
        });

        this.pdf = response.msg;
        this.dialog = false;
      } catch (error) {
        console.log("Error ", error);
      }
    },
  },
};
</script>

<style>
</style>