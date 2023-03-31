<template>
    <v-parallax src="../assets/natty6.webp" class="parallax d-flex align-center justify-center">
        <v-carousel :show-arrows="false" cycle hide-delimiters class="d-flex justify-center" v-if="reviews.length">
            <v-carousel-item v-for="review in reviews" :key="review.id" class="d-flex align-center justify-center flex-row">
                <v-card class="d-flex flex-column align-center bg-primary card">
                    <v-card-title class="text-h5 text-white">{{ review.author_name }}</v-card-title>
                    <v-card-subtitle>
                        {{ review.rating }} étoiles données {{ review.relative_time_description }}
                    </v-card-subtitle>
                    <v-card-text class="text-h6">{{ review.text }}</v-card-text>
                </v-card>
            </v-carousel-item>
        </v-carousel>
    </v-parallax>
</template>

<script>
import useGoogleReviews from "@/composables/useGoogleReviews";

export default {
    setup() {
        const { reviews, fetchReviews } = useGoogleReviews();
        fetchReviews();
        return {
            reviews,
            fetchReviews,
        };
    },
};
</script>

<style scoped>
.card{
    height: auto;
    width: 500px;
}
.parallax{
    height: 600px;
}
.blur{
    filter: blur(4px);
}
</style>