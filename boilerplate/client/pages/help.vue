<template>
  <div>
    <h1>help</h1>
    <h2>1SSR: \{{ data.hello }}</h2>
    <p>\{{ userAgent }}</p>
    <div class="box">
      box
    </div>
    <div>GOTO: <nuxt-link prefetch to="/">index</nuxt-link> / help</div>
    <img width="100%" src="~assets/lark.png" alt="">
    <img width="100%" src="/public/lark.png" alt="">
  </div>
</template>
<script>
export default {
  // default
  // layout: 'default',
  head: {
    title: 'TITLE'
  },
  data() {
    return {
      hi: 'Hello'
    }
  },
  async asyncData({ req, app, env }) {
    // await app.$axios.$post('/api', {
    //   name: 'name',
    //   hi: 'xx'
    // })
    console.log('ENV', env)

    const data =
      (await app.$axios.$get('/api').catch(err => console.log('API:', err))) ||
      {}
    const userAgent = req ? req.headers['user-agent'] : navigator.userAgent
    return { data, server: !!process.server, userAgent }
  }
}
</script>
<style scoped lang="stylus">
@import '~assets/helper.styl'

h1
  color gray(85)

.box
  retina-border(0 0 1px, solid, #999)
  width 100px
  height 100px
  background #eee
  // background #f00
  font-size 50px
  // color var(--mainColor)
  // background white svg(square param(--color #f00))
</style>
