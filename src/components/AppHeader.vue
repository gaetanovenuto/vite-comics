<script>
/* 
    Per importare ed utilizzare un componente dentro un altro devo SEMPRE seguire questi 3 passi:
    1) Importazione del componente
    2) Dichiarazione del componente
    3) Utilizzo del componente
*/

export default {
  data() {
    return {
        menuLinks: [
        {
          label: 'Characters',
          url: '#',
          active: false
        },
        {
          label: 'Comics',
          url: '#',
          active: true
        },
        {
          label: 'Movies',
          url: '#',
          active: false
        },
        {
          label: 'Tv',
          url: '#',
          active: false
        },
        {
          label: 'Games',
          url: '#',
          active: false
        },
        {
          label: 'Collectibles',
          url: '#',
          active: false
        },
        {
          label: 'Videos',
          url: '#',
          active: false
        },
        {
          label: 'Fans',
          url: '#',
          active: false
        },
        {
          label: 'News',
          url: '#',
          active: false
        },
        {
          label: 'Shop',
          url: '#',
          active: false
        },
      ],
    }
  },
  components: {
    
    }
}
</script>

<!-- All'interno del template ci va un solo elemento -->
<template> 
  <div>
    <header>
        <div class="blackbar">
        </div>
        <div class="container">
            <img src="../../public/img/dc-logo.png" alt="DC Comics">
            <ul class="navbar">
                <li v-for="(link, index) in menuLinks" :key="index">
                    <a :href="link.url" :class="{
                    'active': link.active
                    }">
                        {{ link.label }}
                    </a>
                </li>
            </ul>
        </div>
    </header>
  </div>
</template>

<style lang="scss" scoped>
@use '../assets/scss/partials/mixins.scss' as *;
@use '../assets/scss/partials/variables.scss' as *;

header {
    height: 125px;

    .container {
        display: flex;
        align-items: center;
        justify-content: space-between;
    }

    img {
        padding: 10px 0;
    }

    ul {
        display: flex;
        list-style: none;

        li {
            a {
                text-decoration: none;
                color: #0E0E0E;
                font-size: 14px;
                font-weight: 700;
                padding: 46px 8px;
                text-transform: uppercase;
                -webkit-transform: scale(.8, 1);
                display: inline-block;
                position: relative;
            }
        }
    }

    .active {
        color: $blueDC;
    }

    .active::after {
        content: '';
        position: absolute;
        left: 0;
        bottom: 0;
        width: 100%;
        height: 8px;
        background-color: $blueDC;
    }
}


</style>