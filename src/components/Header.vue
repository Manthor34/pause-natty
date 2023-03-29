<template>

    <div class="container" fluid>

        <v-parallax src="../assets/natty2.webp" class="parallax d-flex align-center justify-center">
            <div class="d-flex flex-column align-center text rounded">
                <h1 class="text-primary text-h1 font-weight-bold my-8">Mangez en Conscience</h1>
                <p class="text-white text-h4 my-8">Notre buffet libre-service est organisé en fonction des macro-nutriments contenus dans les ingrédients,
                composez-vous un repas en parfaite adéquation avec les besoins de votre corps</p>
                <v-btn class="my-8 bg-secondary">Livraison</v-btn>
            </div>
        </v-parallax>
        

    </div>

</template>

<script>
export default {

}
</script>

<style scoped>
.container {
    margin: 0;
    width: 100%;
    height: 900px;
}
.text{
    margin: 10%;
    text-shadow: 2px 2px 5px black;
}

</style>