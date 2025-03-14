<template>


  <main>
    <router-view />
  </main>

</template>

<script>
import { computed } from 'vue';
import { useRoute } from 'vue-router';
import { AppState } from './AppState';

export default {
  setup() {
    const route = useRoute()
    return {
      appState: computed(() => AppState),
      hideNavbar: computed(() => route.meta?.hideNavbar),
      hideFooter: computed(() => route.meta?.hideFooter)
    }
  }
}
</script>
<style lang="scss">
@import "./assets/scss/main.scss";

::-webkit-scrollbar{
  width: 20px
}
::-webkit-scrollbar-track{
  background-color: rgb(219, 219, 219);
}
::-webkit-scrollbar-thumb{
  background: linear-gradient(to bottom, rgb(46, 204, 113), rgb(108, 92, 231));
}
</style>
