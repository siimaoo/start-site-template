<template>
  <v-app>
    <v-main>
      <Toolbar />
      <v-container>
        <nuxt />
      </v-container>
      <Footer />
    </v-main>
  </v-app>
</template>

<script>
import { Toolbar, Footer } from '~/components'
export default {
  components: {
    Toolbar,
    Footer,
  },
}
</script>
