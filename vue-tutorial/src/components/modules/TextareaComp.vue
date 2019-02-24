<template>
  <div>
    <p class="error">{{ error }}</p>
    <textarea v-model="impression"></textarea>
  </div>
</template>

<script>
import {mapGetters} from 'vuex'

export default {
  name: 'TextareaComp',
  computed: {
    impression: {
      get () {
        return this.$store.state.impression
      },
      set (value) {
        this.$store.commit('updateImpression', value)
      }
    },
    ...mapGetters('Textarea', {
      'error': ''
    })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.error {
  color: #ff0000;
}
</style>
