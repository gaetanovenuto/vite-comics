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
            
        }
    },
    props: {
        singleItem: Object
    },
    components: {
        
        }
}
</script>

<!-- All'interno del template ci va un solo elemento -->
<template> 
    <div class="single-comic">
        <div>
            <img :src="singleItem.thumb" :alt="singleItem.series">
        </div>
        <div class="comic-name">
            {{ singleItem.series }}
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../assets/scss/partials/mixins.scss' as *;
@use '../assets/scss/partials/variables.scss' as *;

main {
    .single-comic {
        width: calc(100% / 6);
        height: 250px;
        

        img {
            width: 175px;
            height: 175px;
            object-fit: cover;
        }

        .comic-name {
            color: white;
            font-size: 15px;
            text-transform: uppercase;
            padding-top: 10px;
        }
    }
}

</style>