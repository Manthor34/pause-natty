<template>
    <h3 class="text-center">Reviews Google (méthode du bled json) mais personnalisable</h3>

    <v-carousel hide-delimiters>
        <v-carousel-item v-for="review in reviews" :key="review.id">
            <v-card>
                <v-card-title class="text-h5">{{ review.author_name }}</v-card-title>
                <v-card-subtitle>
                    {{ review.rating }} étoiles données {{ review.relative_time_description }}
                </v-card-subtitle>
                <v-card-text>{{ review.text }}</v-card-text>
            </v-card>
        </v-carousel-item>
    </v-carousel>
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
iframe {
    min-height: 550px;
    min-width: 1000px;
    z-index: 1;
}



div {
    border: 1px solid #e0e0e0;
    border-radius: 4px;
    padding: 16px;
}

h3 {
    margin: 0;
    font-size: 1.25rem;
    font-weight: bold;
}

ul {
    margin: 16px 0 0;
    padding: 0;
    list-style: none;
}

li {
    margin: 16px 0;
}

li p {
    margin: 0;
    font-size: 1rem;
    line-height: 1.5;
}

li p:first-of-type {
    font-weight: bold;
}

li p:nth-of-type(2) {
    color: #f57c00;
    margin-top: 8px;
    margin-bottom: 4px;
}

li p:nth-of-type(3) {
    margin-top: 4px;
    font-style: italic;
}
</style>