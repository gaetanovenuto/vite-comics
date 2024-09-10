<script>
/* 
    Per importare ed utilizzare un componente dentro un altro devo SEMPRE seguire questi 3 passi:
    1) Importazione del componente
    2) Dichiarazione del componente
    3) Utilizzo del componente
*/

import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppFooter from './components/AppFooter.vue';

export default {
  data() {
    return {
      
          
    }
  },
  components: {
        AppHeader,
        AppMain,
        AppFooter
    }
}
</script>

<!-- All'interno del template ci va un solo elemento -->
<template> 
  <div>
    <AppHeader />
    <AppMain />
    <AppFooter />   
  </div>
</template>

<style lang="scss" scoped>
</style>
