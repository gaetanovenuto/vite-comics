<script>
/* 
    Per importare ed utilizzare un componente dentro un altro devo SEMPRE seguire questi 3 passi:
    1) Importazione del componente
    2) Dichiarazione del componente
    3) Utilizzo del componente
*/

import AppMainShop from './AppMainShop.vue';
import AppSingleComic from './AppSingleComic.vue';

export default {
  data() {
    return {
        DCComics: [
            {
                thumb: "https://www.coverbrowser.com/image/action-comics/1-1.jpg",
                price: "$19.99",
                series: "Action Comics",
                type: "comic book",
            },
            {
                thumb: "https://www.panini.it/media/catalog/product/cache/a5b5dd3adfe0d321084804c738f29601/M/1/M1BLLA015ISBN_0.jpg",
                price: "$3.99",
                series: "American Vampire 1976",
                type: "comic book",
            },
            {
                thumb: "https://media.wired.com/photos/593384dad80dd005b42b2817/master/w_2560%2Cc_limit/Aquaman-16.jpg",
                price: "$16.99",
                series: "Aquaman",
                type: "graphic novel",
            },
            {
                thumb: "https://d29xot63vimef3.cloudfront.net/image/batgirl/1-1.jpg",
                price: "$2.99",
                series: "Batgirl",
                type: "comic book",
            },
            {
                thumb: "https://static.posters.cz/image/750/locandine-film-in-plexiglass-batman-prowl-comic-cover-i69653.jpg",
                price: "$3.99",
                series: "Batman",
                type: "comic book",
            },
            {
                thumb: "https://static.wikia.nocookie.net/marvel_dc/images/5/50/Batman_Beyond_v.1_1.jpg",
                price: "$2.99",
                series: "Batman Beyond",
                type: "comic book",
            },
            {
                thumb: "https://static.wikia.nocookie.net/marvel_dc/images/0/0d/Batman_Superman_Vol_1_1.jpg",
                price: "$3.99",
                series: "Batman/Superman",
                type: "comic book",
            },
            {
                thumb: "https://static.wikia.nocookie.net/marvel_dc/images/c/cf/Batman_Superman_Annual_Vol_2_1.jpg",
                price: "$4.99",
                series: "Batman/Superman Annual",
                type: "comic book",
            },
            {
                thumb: "https://static.wikia.nocookie.net/marvel_dc/images/5/54/Batman_The_Joker_War_Zone_Vol_1_1.jpg",
                price: "$5.99",
                series: "Batman: The Joker War Zone",
                type: "comic book",
            },
            {
                thumb: "https://static.wikia.nocookie.net/marvel_dc/images/6/64/Batman_Three_Jokers_Collected.jpg",
                price: "$6.99",
                series: "Batman: Three Jokers",
                type: "comic book",
            },
            {
                thumb: "https://static.wikia.nocookie.net/marvel_dc/images/f/f8/Batman_White_Knight_Presents_Harley_Quinn_Vol_1_1.jpg",
                price: "$4.99",
                series: "Batman: White Knight Presents: Harley Quinn",
                type: "comic book",
            },
            {
                thumb: "https://static.wikia.nocookie.net/marvel_dc/images/c/c8/Catwoman_Vol_2_1.jpg",
                price: "$16.99",
                series: "Catwoman",
                type: "graphic novel",
            },
        ]
    }
},
  components: {
        AppSingleComic,
        AppMainShop
    }
}
</script>

<!-- All'interno del template ci va un solo elemento -->
<template> 
  <div>
    <main>  
        <div class="jumbotron">
            <img src="../../public/img/jumbotron.jpg" alt="DC Comics">
        </div> 
        <div class="comics">
            <div class="container">
                <div class="current-series">
                    Current Series
                </div>        
            </div>
            <div class="main-content">
                <div class="container">
                    <div class="comics-list">
                        <AppSingleComic
                            v-for="(comics, index) in DCComics"
                            :key="index"
                            :singleItem="comics" />
                        <button class="load-more">
                            Load More
                        </button>
                    </div>    
                </div>
            </div>
        </div>
        <AppMainShop />
    </main>
  </div>
</template>

<style lang="scss" scoped>
@use "../assets/scss/partials/mixins.scss" as *;
@use "../assets/scss/partials/variables.scss" as *;

main {
    .jumbotron {

        img {
            width: 100vw;
            object-fit: fill;
            z-index: -1;
            position: relative;
        }
    }

    .comics {
        background-color: #303030;
        height: 660px;
        width: 100vw;
        position: absolute;
        top: 550px; 

        .container:first-child {
            height: 75px;
        }

        .container {
            height: 125px;
            width: 100%;
            @include flex-align-center;
            position: relative;

            .current-series {
                color: white;
                background-color: $blueDC;
                text-transform: uppercase;
                padding: 12px 35px;
                font-size: 20px;
                font-weight: 700;
                -webkit-transform: scale(.8, 1);
                position: absolute;
                top: -25px;
            }

            .comics-list {
                display: flex;
                flex-wrap: wrap;
                width: 100%;
                margin-top: 500px;

                .load-more {
                    color: white;
                    background-color: $blueDC;
                    text-transform: uppercase;
                    padding: 10px 100px;
                    font-size: 20px;
                    font-weight: 700;
                    -webkit-transform: scale(.8, 1);
                    margin: 10px auto;

                    &:hover {
                        cursor: pointer;
                    }
                }
            }
        }
    } 
}
</style>