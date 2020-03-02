<template lang="pug">
  BaseLayout
    template(v-slot:default)
      transition(appear)
        Typography(
          :level="1"
          text="59 Split Layout"
        )
      Base59System
</template>

<script>
import BaseLayout from '@/components/Template/BaseLayout.vue'
import Typography from '@/components/Atom/Typography/index.vue'
import Base59System from '@/components/Molecule/Base59System/index.vue'

export default {
  name: 'PageIndex',
  components: {
    BaseLayout,
    Typography,
    Base59System,
  },
}
</script>

<style lang="sass" module>
.logo
  margin: 0 auto
</style>
