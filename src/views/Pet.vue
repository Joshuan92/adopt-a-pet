<template>
    <div>
        <h1>Name: {{ animal.name }}</h1>
        <p>Species: {{ species }}</p>
        <p>Age: {{ animal.age }} years old</p>
        <p>Breed: {{ animal.breed }}</p>
    </div>
</template>

<script>
import { mapState } from 'vuex'

export default {
  data () {
    return {
      animal: {},
      species: ''
    }
  },
  computed: {
    ...mapState([
      'cats',
      'dogs'
    ])
  },
  mounted () {
    this.animal = this[this.$route.params.species][this.$route.params.id]
    this.species = this.$route.params.species
  }
}
</script>
