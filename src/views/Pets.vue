<template>
  <div>
    <h1>Name: {{ animal.name }}</h1>
    <p>Breed: {{ animal.breed }} ({{$route.params.species}})</p>
    <p>{{ animal.age }} years old</p>
  </div>
</template>

<script>
import { mapState } from 'vuex'

export default {
  data () {
    return {
      animal: {}
    }
  },
  computed: {
    ...mapState([
      'cats',
      'dogs'
    ])
  },
  mounted () {
    const animal = this[this.$route.params.species][this.$route.params.id]
    this.animal = animal
  }
}
</script>

<style>

</style>
