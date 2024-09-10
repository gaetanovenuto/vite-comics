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
        
      ],
      footerDCComicsInfo: [
        {
          label: 'Characters',
          url: '#'
        },
        {
          label: 'Comics',
          url: '#'
        },
        {
          label: 'Movies',
          url: '#'
        },
        {
          label: 'TV',
          url: '#'
        },
        {
          label: 'Games',
          url: '#'
        },
        {
          label: 'Videos',
          url: '#'
        },
        {
          label: 'News',
          url: '#'
        },
      ],
      footerShopInfo: [
        {
          label: 'Shop DC',
          url: '#'
        },
        {
          label: 'Shop DC Collectibles',
          url: '#'
        }      
      ],
      footerDCInfo: [
        {
          label: 'Terms Of Use',
          url: '#'
        },
        {
          label: 'Privacy Policy (New)',
          url: '#'
        },
        {
          label: 'Ad Choices',
          url: '#'
        },
        {
          label: 'Advertising',
          url: '#'
        },
        {
          label: 'Jobs',
          url: '#'
        },
        {
          label: 'Subscriptions',
          url: '#'
        },
        {
          label: 'Talent Workshops',
          url: '#'
        },
        {
          label: 'CPSC Certificates',
          url: '#'
        },
        {
          label: 'Ratings',
          url: '#'
        },
        {
          label: 'Shop Help',
          url: '#'
        },
        {
          label: 'Contact Us',
          url: '#'
        },
      ],
      footerSites: [
        {
          label: 'DC',
          url: '#'
        },
        {
          label: 'MAD Magazine',
          url: '#'
        },
        {
          label: 'DC Kids',
          url: '#'
        }, 
        {
          label: 'DC Universe',
          url: '#'
        }, 
        {
          label: 'DC Power Visa',
          url: '#'
        }    
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
    <div class="blackbar">

    </div>
    <header>
      <div class="container">
        <img src="../public/img/dc-logo.png" alt="DC Comics">
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
    <footer>
      <div class="footer-info">
        <div class="container">
          <div class="row">
            <div class="col-1-3">
              <div class="row">
                <div class="col-1-3">
                  <div class="info-dc-comics">
                    <h2>
                      DC Comics
                    </h2>
                    <ul>
                        <li v-for="(link, index) in footerDCComicsInfo" :key="index">
                            <a :href="link.url" :alt="link.label">
                            {{ link.label }}
                        </a>
                      </li>
                    </ul>
                  </div>
                  <div class="info-shop">
                    <h2>
                      Shop
                    </h2>
                    <ul>
                        <li v-for="(link, index) in footerShopInfo" :key="index">
                            <a :href="link.url" :alt="link.label">
                            {{ link.label }}
                        </a>
                      </li>
                    </ul>
                  </div>
                </div>
                <div class="col-1-3">
                    <div class="info-dc">
                        <h2>
                            DC
                        </h2>
                        <ul>
                            <li v-for="(link, index) in footerDCInfo" :key="index">
                                <a :href="link.url" :alt="link.label">
                                {{ link.label }}
                            </a>
                        </li>
                        </ul>
                    </div>
                </div>
                <div class="col-1-3">
                    <div class="info-sites">
                        <h2>
                            Sites
                        </h2>
                        <ul>
                            <li v-for="(link, index) in footerSites" :key="index">
                                <a :href="link.url" :alt="link.label">
                                {{ link.label }}
                            </a>
                        </li>
                        </ul>
                    </div>
                </div>
              </div>
            </div>
            <div class="dc-logo">
            </div>
          </div>
        </div>
      </div>
    </footer>
    
  </div>
</template>

<style scoped>

.blackbar {
  min-height: 15px;
  background-color: #0E0E0E;
}

header {
  height: 125px;
  background-color: rgb(169, 169, 241);
  
}

header .container {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

header img {
  padding: 10px 0;
}

header ul {
  display: flex;
  list-style: none
}

header ul li a {
  text-decoration: none;
  color: #0E0E0E;
  font-size: 14px;
  font-weight: 700;
  padding: 53px 8px;
  text-transform: uppercase;
  -webkit-transform: scale(.8, 1);
  display: inline-block;
  position: relative;
}

.active {
  color: #0282F9;
}

.active::after {
    content: '';
    position: absolute;
    left: 0;
    bottom: 0;
    width: 100%;
    height: 8px;
    background-color: #0282F9;
}

main .blackbar .container {
  height: 125px;
  width: 100%;
  display: flex;
  align-items: center;
}

main .container .main-content {
  color: white;
  font-size: 26px;
  font-weight: bold;
  -webkit-transform: scale(.8, 1);
  display: inline-block;
}

main .shop {
  background-color: #0282F9;
}

main .shop .container {
  height: 150px;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
}

main .shop .shop-navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  list-style: none;
}

main .shop .shop-navbar li{
  padding: 0 25px;
}

main .shop .shop-navbar img {
  height: 60px;
  margin: 0 10px;
}

main .shop .shop-navbar li:last-child img {
  height: 40px;
}

main .shop .shop-navbar li a{
  text-decoration: none;
  text-transform: uppercase;
  color: white;
  font-size: 14px;
  display: flex;
  align-items: center;
}

footer .footer-info {
  width: 100%;
  height: 375px;
  background-image: url('../public/img/footer-bg.jpg');
}

footer .row {
    display: flex;
    justify-content: space-between;
}

footer h2 {
    color: white;
    text-transform: uppercase;
    -webkit-transform: scale(.8, 1);
    margin: 0 -15px;
}

footer li a{
  text-decoration: none;
  color: rgba(255, 255, 255, 0.596);
  font-size: 12px;
  font-weight: 100;
  display: flex;
  align-items: center;
  padding: 2px 0;
}

footer ul {
  list-style: none;
  padding: 10px 0;
}

footer .col-1-3 {
    padding: 20px 0;
}

footer .dc-logo {
    background-image: url('../public/img/dc-logo-bg.png');
    width: 600px;
    z-index: 999;
    margin-top: -100px;
    background-repeat: no-repeat;
}
</style>
