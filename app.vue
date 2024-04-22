<template>
  <NuxtLayout>
    <v-app>
      <transition name="fade">
          <v-container grid-list-xl>
            <NuxtPage />
          </v-container>
        </transition>
    </v-app>
  </NuxtLayout>
</template>