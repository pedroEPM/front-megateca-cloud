<template>

    <v-card @click="sendOnlyPDF()">
    <v-img
        width="100%"
        height="auto"
        :src="image"
        cover
    ></v-img>

    <v-card-item>
      <v-card-title>{{ publication }}</v-card-title>

      <v-card-subtitle>
        <span class="me-1">{{ cChangedDateFormat(date) }}</span>
      </v-card-subtitle>
    </v-card-item>

    <v-card-text>
      <div>
        {{ notebook }}
      </div>
    </v-card-text>
  </v-card>

</template>

<script>
export default {
  data: () => ({}),
  props: {
    publication: {
      type: String,
      require: true
    },
    notebook: {
      type: String,
      require: true
    },
    date: {
      type: String,
      require: true,
    },
    image: {
      type: String,
      require: true
    },
    newId: {
      type: String,
      require: true
    }
  },
  methods: {
    setMont(index) {
      const months = ['Enero', 'Febrero', 'Marzo', 'Abril', 'Mayo', 'Junio', 'Julio', 'Agosto', 'Septiembre', 'Octubre', 'Noviembre', 'Diciembre']
      return months[index];
    },
    cChangedDateFormat(date) {
      const newDate = new Date(date).toISOString().substring(0,10).split('-');
      return newDate[2] + '-' + this.setMont(Number(newDate[1] - 1)) + '-' + newDate[0];
    },
    sendOnlyPDF() {
      this.$router.push({
        path: '/search_',
        query: {
          id: this.newId.replace('P-', ''),
        }
      })
    },
    searchByText() {
    console.log("Buscando por texto:", this.searchQuery);
    },
    searchByDate() {
      console.log("Buscando desde:", this.startDate, "hasta:", this.endDate);
    },
  }
};
</script>

<style scoped>

</style>