<template>
  <div>
    <v-app-bar color="white" prominent height="80">
      <v-row align="center" class="h-100">
        <v-app-bar-nav-icon @click.stop="drawer = !drawer" />

        <div>Logo</div>
      </v-row>
    </v-app-bar>

    <v-navigation-drawer v-model="drawer" absolute bottom temporary>
      <v-list nav dense>
        <v-list-item-group
          v-model="group"
          active-class="deep-purple--text text--accent-4"
        >
          <v-list-item v-for="(link, index) in links" :key="index">
            <v-list-item-title>
              <NuxtLink :to="link.link">{{ link.title }}</NuxtLink>
            </v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
  </div>
</template>

<script>
export default {
  data: () => ({
    drawer: false,
    group: null,
    links: [{ title: 'Página Incial', link: '/' }],
  }),

  watch: {
    group() {
      this.drawer = false
    },
  },
}
</script>
