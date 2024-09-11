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
        shopLinks: [
        {
          label: 'Digital Comics',
          url: '#',
          img: '../public/img/buy-comics-digital-comics.png'
        },
        {
          label: 'DC Merchandise',
          url: '#',
          img: '../public/img/buy-comics-merchandise.png'
        },
        {
          label: 'Subscription',
          url: '#',
          img: '../public/img/buy-comics-subscriptions.png'
        },
        {
          label: 'Comic Shop Locator',
          url: '#',
          img: '../public/img/buy-comics-shop-locator.png'
        },
        {
          label: 'DC Power Visa',
          url: '#',
          img: '../public/img/buy-dc-power-visa.svg'
        },
        
      ]
    }
  },
  components: {
    
    }
}
</script>

<!-- All'interno del template ci va un solo elemento -->
<template> 
  <div>
    <main>
        <div class="shop">
            <div class="container">
                <div class="shop-content">
                    <ul class="shop-navbar">
                        <li v-for="(link, index) in shopLinks" :key="index">
                            <a :href="link.url">
                                <img :src="link.img" :alt="link.label">
                                {{ link.label }}
                            </a>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </main>
  </div>
</template>

<style lang="scss" scoped>
@use '../assets/scss/partials/mixins.scss' as *;
@use '../assets/scss/partials/variables.scss' as *;

main {
    .shop {
        background-color: $blueDC;

        .container {
            height: 150px;
            width: 100%;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .shop-navbar {
            @include ul-format;
            @include flex-align-center;
            justify-content: space-between;

            li {
                padding: 0 25px;
                z-index: 999;

                &:last-child {
                    img {
                        height: 40px;
                    }
                }

                a {
                    text-decoration: none;
                    text-transform: uppercase;
                    color: white;
                    font-size: 14px;
                    @include flex-align-center;
                }
            }

            img {
                height: 60px;
                margin: 0 10px;
            }
        }
    }
}
</style>