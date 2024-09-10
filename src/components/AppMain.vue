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
        <div class="blackbar">
            <div class="container">
                <div class="main-content">
                    --&gt; Content goes here &lt;--
                </div> 
            </div>
        </div>
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
    .blackbar {
        .container {
            height: 125px;
            width: 100%;
            display: flex;
            align-items: center;

            .main-content {
                color: white;
                font-size: 26px;
                font-weight: bold;
                -webkit-transform: scale(.8, 1);
                display: inline-block;
            }
        }
    }
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
            display: flex;
            justify-content: space-between;
            align-items: center;
            list-style: none;

            li {
                padding: 0 25px;

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
                    display: flex;
                    align-items: center;
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