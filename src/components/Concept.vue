<template>
    <v-container id="section-concept" class="d-flex flex-column align-center text-center containerConcept" fluid>
        <h3 class="text-h2 my-8 text-primary alkatra" transition="v-tab-transition">CONCEPT</h3>
        <v-container class="d-flex flex-column flex-md-row">
            <p class="text-h5 my-8 px-12 alkatra">
                <span class="text-h4 alkatra">Sain</span><br>Toutes nos préparations sont réalisées à partir de produits bruts. Les viandes, les poissons et
                les
                légumes
                sont cuits à la vapeur pour préserver leurs nutriments, vitamines et sels minéraux.
            </p>
            <p class="text-h5 my-8 px-12 alkatra">
                <span class="text-h4 alkatra">Rapide</span><br>Lavez-vous les mains, choisissez la taille de votre bol en fonction de votre appétit et
                servez-vous
                directement ce qui vous fait envie.
            </p>

            <p class="text-h5 my-8 px-12 alkatra">
                <span class="text-h4 alkatra">Pas cher</span><br>Vous faire participer à la confection de votre repas nous permet de fonctionner en équipe
                réduite.
                Une
                économie qui se ressent sur nos prix, enfin un lieu où manger sain sans se ruiner !
            </p>
        </v-container>
    </v-container>
</template>

<script>

export default {

}
</script>

<style scoped>
    .alkatra{
        font-family: 'Alkatra', cursive !important;
    }
    .containerConcept{
        border-bottom: 2px solid grey;
        width: 90% ;
    }

</style>