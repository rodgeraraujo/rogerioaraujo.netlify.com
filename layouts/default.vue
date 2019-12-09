<template>
  <main class="default">
    <transition name="layout" mode="out-in">
      <nuxt></nuxt>
    </transition>
  </main>
</template>

<script>
export default {
  name: 'defaultLayout'
}
</script>

<style lang="stylus">
</style>
