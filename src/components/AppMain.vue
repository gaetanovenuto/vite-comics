<script>
/* 
    Per importare ed utilizzare un componente dentro un altro devo SEMPRE seguire questi 3 passi:
    1) Importazione del componente
    2) Dichiarazione del componente
    3) Utilizzo del componente
*/

import AppMainShop from './AppMainShop.vue';

export default {
  data() {
    return {
    }
  },
  components: {
        AppMainShop
    }
}
</script>

<!-- All'interno del template ci va un solo elemento -->
<template> 
  <div>
    <main>
        <div class="blackbar">
            <div class="container">
                <div class="main-content">
                    --&gt; Content goes here &lt;--
                </div> 
            </div>
        </div>
        <AppMainShop />
    </main>
  </div>
</template>

<style lang="scss" scoped>
@use '../assets/scss/partials/mixins.scss' as *;
@use '../assets/scss/partials/variables.scss' as *;

main {
    .blackbar {
        .container {
            height: 125px;
            width: 100%;
            @include flex-align-center;

            .main-content {
                color: white;
                font-size: 26px;
                font-weight: bold;
                -webkit-transform: scale(.8, 1);
                display: inline-block;
            }
        }
    }
}
</style>