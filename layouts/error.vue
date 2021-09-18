<template>
  <v-app dark>
    <h1 v-if="error.statusCode === 404">
      {{ pageNotFound }}
    </h1>
    <h1 v-else>
      {{ otherError }}
    </h1>
    <v-img src="https://images.pexels.com/photos/374918/pexels-photo-374918.jpeg?cs=srgb&dl=pexels-george-becker-374918.jpg&fm=jpg" max-height="300"
  max-width="500" class="image-erreur"></v-img>
    <NuxtLink to="/">
      Revenir à la page principale
    </NuxtLink>
  </v-app>
</template>

<script>
export default {
  layout: 'empty',
  props: {
    error: {
      type: Object,
      default: null
    }
  },
  data () {
    return {
      pageNotFound: '404 Not Found',
      otherError: 'An error occurred'
    }
  },
  head () {
    const title =
      this.error.statusCode === 404 ? this.pageNotFound : this.otherError
    return {
      title
    }
  }
}
</script>

<style scoped>

h1 {
  font-family: 'special_eliteregular';
  font-size: 5em;
  color: #BD005A;
  margin-left: auto;
  margin-right: auto;
  text-justify: center;
}
a:link{
  font-size: 1.5em;
  margin-left: auto;
  margin-right: auto;
  }
  
a:hover{
  font-size: 1.5em;
  margin-left: auto;
  margin-right: auto;
  font-weight: bold;
  }
.image-erreur{
  margin: 25px auto 25px auto;
}
</style>
