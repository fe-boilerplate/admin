<template>
  <ModuleList :routes="routes" :activeName="activeName" :meta="meta" />
</template>
<style scoped>
</style>
<script>
import { mapState } from 'vuex'
import ModuleList from '~/components/index/ModuleList'
export default {
  layout: 'entry',
  data() {
    return {
      input: '',
      activeName: 'first'
    }
  },
  methods: {
    handleClick() {}
  },
  computed: {
    ...mapState(['user', 'meta']),
    routes() {
      return this.$router.options.routes
    }
  },
  components: {
    ModuleList
  }
}
</script>
