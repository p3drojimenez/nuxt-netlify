<template>
  <v-layout
    justify-center
    align-center
  >
    <v-flex
      xs12
      sm6
      md6
    >
      <v-card v-for="exp in data.data">
        <v-img
          :src="exp.file"
          aspect-ratio="2.75"
        ></v-img>
        <p>{{ exp.name }}</p>
        <p>{{ exp.city.name }} </p>
        <p>{{ exp.langs }}</p>
        <v-card-actions>
          <v-btn flat color="orange">Share</v-btn>
          <v-btn flat color="orange">Explore</v-btn>
        </v-card-actions>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
import axios from 'axios'
export default {
  components: {
  },
  data() {
    return {
      data: ''
    }
  },
  mounted() {
    axios.get('http://api.baccoexperiences.com/api/publics/experiences')
    .then(response => (this.data = response))
  }
}
</script>
