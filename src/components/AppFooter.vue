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
      socialLogos: [
        {
            label: 'Facebook',
            img: '../public/img/footer-facebook.png',
            url: '#'
        },
        {
            label: 'Twitter',
            img: '../public/img/footer-twitter.png',
            url: '#'
        },
        {
            label: 'Youtube',
            img: '../public/img/footer-youtube.png',
            url: '#'
        },
        {
            label: 'Pinterest',
            img: '../public/img/footer-pinterest.png',
            url: '#'
        },
        {
            label: 'Periscope',
            img: '../public/img/footer-periscope.png',
            url: '#'
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
        <div class="footer-social">
            <div class="container">
                <a href="#" class="sign-up-link">
                    Sign-up now!
                </a>
                <div class="socials">   
                    <ul>
                        <li>
                            <a href="#" class="follow-us">
                                Follow us
                            </a>
                        </li>
                        <li v-for="(link, index) in socialLogos" :key="index">
                            <a :href="link.url">
                                <img :src="link.img" :alt="link.label">
                            </a>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
        <div class="blackbar">
        </div> 
    </footer>
  </div>
</template>

<style lang="scss" scoped>
@use '../assets/scss/partials/mixins.scss' as *;
@use '../assets/scss/partials/variables.scss' as *;

footer {
    .footer-info {
        width: 100%;
        height: 375px;
        background-image: url('../public/img/footer-bg.jpg');
    }

    .row {
        display: flex;
        justify-content: space-between;
    }

    h2 {
        color: white;
        text-transform: uppercase;
        -webkit-transform: scale(.8, 1);
        margin: 0 -17px;
    }

    ul {
        list-style: none;
        padding: 10px 0;
    }

    li {
        a {
            text-decoration: none;
            color: rgba(255, 255, 255, 0.596);
            font-size: 12px;
            font-weight: 100;
            display: flex;
            align-items: center;
            padding: 2px 0;
        }
    }

    .col-1-3 {
        padding: 20px 0;
    }

    .dc-logo {
        background-image: url('../public/img/dc-logo-bg.png');
        width: 600px;
        margin-top: -100px;
        background-repeat: no-repeat;
    }

    .footer-social {
        background-color: #303030;
        width: 100%;
        height: 105px;

        .container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            height: 100%;
        }

        .socials {
            ul {
                display: flex;
                justify-content: space-between;

                li {
                    padding: 0 10px;
                }
            }
        }
    }

    .sign-up-link {
        color: white;
        text-decoration: none;
        font-size: 18px;
        font-weight: 600;
        text-transform: uppercase;
        border: 2px solid $blueDC;
        padding: 10px 15px;
    }

    .follow-us {
        color: $blueDC;
        text-transform: uppercase;
        font-size: 22px;
        font-weight: 700;
        -webkit-transform: scale(.8, 1);
    }
}
</style>