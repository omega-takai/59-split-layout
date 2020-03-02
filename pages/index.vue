<template lang="pug">
  BaseLayout
    template(v-slot:default)
      transition(appear)
        Typography(
          :level="1"
          text="hoge"
        )
</template>

<script>
import BaseLayout from '@/components/Template/BaseLayout.vue'
import Typography from '@/components/Atom/Typography/index.vue'

export default {
  name: 'PageIndex',
  components: {
    BaseLayout,
    Typography,
  },
}
</script>

<style lang="sass" module>
.logo
  margin: 0 auto
</style>
