<template>
  <main class="default">
    <c-header/>
    <transition name="layout" mode="out-in">
      <nuxt></nuxt>
    </transition>
  </main>
</template>

<script>
export default {
  name: 'defaultLayout',
  components: {
    CHeader: () => import('~/components/Header')
  }
}
</script>

<style lang="stylus">
</style>
