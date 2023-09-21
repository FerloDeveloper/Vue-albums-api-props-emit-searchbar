<template>
  <div id="app">
    <BaseHeader/>
    <BaseMain/>
    <BaseFooter/>
  </div>
</template>
<script>
import BaseHeader from './components/macros/BaseHeader.vue'
import BaseMain from './components/macros/BaseMain.vue'
import BaseFooter from './components/macros/BaseFooter.vue'


export default {
  name: 'App',
  components: {
    BaseHeader,
    BaseMain,
    BaseFooter,
  }
}
</script>

<style lang="scss">

  @import './assets/style/global.scss';

  body {
    height: 100vh;
  }

</style>
