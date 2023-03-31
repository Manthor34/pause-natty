<template>
    <h3 class="text-h2 my-8 text-primary text-center mt-12 alkatra">POST INSTA</h3>
    <v-container class="d-flex flex-column align-center">
        <v-container class="bg-secondary mb-8 mt-8 rounded-lg" v-if="posts.length">
            <v-row no-gutters>
                <v-col v-for="post in posts" :key="post.url" cols="12" sm="4">
                    <v-sheet class="ma-2 pa-2 rounded-lg">
                        <a class="" :href="post.redirect" target="_blank">
                            <v-card :text="post.like"></v-card>
                            <v-img aspect-ratio="16/9" cover :src="post.url" alt="url post" class="rounded"></v-img>
                        </a>
                    </v-sheet>
                </v-col>
            </v-row>
        </v-container>

        <v-btn href="https://www.instagram.com/pausenatty/" size="x-large" class=" mb-8 bg-secondary text-h5 button">FOLLOW<v-icon icon="mdi-instagram" class="ml-4"></v-icon></v-btn>
    </v-container>
</template>
  
<script>
import usePostInsta from "@/composables/usePostInsta"

export default {
    setup() {
        const { posts, fetchPosts } = usePostInsta()
        fetchPosts()
        return {
            posts,
            fetchPosts,
        }
    },
};
</script>

<style scoped>
.alkatra{
    font-family: 'Alkatra', cursive !important;
}
.button{
    width: 10%;
    text-align: center;
}
</style>