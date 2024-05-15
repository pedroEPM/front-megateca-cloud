<template>
  <v-app>
    <v-toolbar color="primary" dark class="pl-5 pr-5" fixed>
      <v-toolbar-side-icon>
        <v-img
          src="https://www.megamedia.com.mx/wp-content/uploads/2023/12/logomegamedia.png"
          width="150"
          contain
        ></v-img>
      </v-toolbar-side-icon>

      <v-spacer></v-spacer>
      <v-toolbar-items class="hidden-sm-and-down">
        <section class="cNavBar">
          <p v-for="(item, index) in items" :key="index">
            <NuxtLink :to="item.to"
              ><v-icon>{{ item.icon }}</v-icon> {{ item.title }}</NuxtLink
            >
          </p>
        </section>
      </v-toolbar-items>
      <v-app-bar-nav-icon
        variant="text"
        @click.stop="drawer = !drawer"
        class="hidden-md-and-up"
      ></v-app-bar-nav-icon>
    </v-toolbar>
    <v-navigation-drawer
      v-model="drawer"
      :location="$vuetify.display.mobile ? 'right' : undefined"
      temporary
      floating
    >

    <v-list
          density="compact"
          nav
        >
            <v-list-item router  v-for="(item, index) in items" :key="index" :prepend-icon="item.icon" :title="item.title" :to="item.to">
        
        
            </v-list-item>
          <!-- <v-list-item prepend-icon="mdi-forum" title="About" value="about"></v-list-item> -->
    </v-list>
     
    </v-navigation-drawer>
    <v-content>
      <v-container fluid>
        <slot />
      </v-container>
    </v-content>
    <v-footer class="d-flex flex-column pa-0">
    <div class="px-4 py-2 bg-black text-center w-100">
      {{ new Date().getFullYear() }} — <strong>Megamedia</strong>
    </div>
  </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
    drawer: false,
      group: null,
      items: [
        {
          icon: "mdi-home",
          title: "Home",
          to: "/",
        },
        {
          icon: "mdi-magnify",
          title: "Búsqueda",
          to: "/search",
        },
      ],
    };
  },
  watch: {
    group() {
      this.drawer = false;
    },
  },
};
</script>

<style scoped>
.cNavBar {
  display: flex;
  width: 100%;
  height: auto;
  flex-wrap: wrap;
  gap: 1em;
  align-content: center;
}

.cNavBar p {
  margin: 0;
}

.cNavBar p a {
  color: white !important;
  text-decoration: none;
}
</style>