<template>
  <div>
    <h1 v-if="error.statusCode === 404">
      {{ pageNotFound }}
    </h1>
    <h1 v-else>
      {{ otherError }}
    </h1>
    <NuxtLink to="/"> Voltar para página inicial </NuxtLink>
  </div>
</template>

<script>
export default {
  layout: 'empty',
  props: {
    error: {
      type: Object,
      default: null,
    },
  },
  data() {
    return {
      pageNotFound: '404 Página não encontrada!',
      otherError:
        'Oops! Algum erro desconhecido ocorreu, tente novamente mais tarde!',
    }
  },
  head() {
    const title =
      this.error.statusCode === 404 ? this.pageNotFound : 'Erro desconhecido'
    return {
      title,
    }
  },
}
</script>
