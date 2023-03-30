<template>
    <h3 class="text-h2 my-8 text-primary text-center mt-12">POST INSTA</h3>

    <v-container class="bg-secondary mb-8 mt-8" v-if="posts.length">
        <v-row no-gutters>
            <v-col v-for="post in posts" :key="post.url" cols="12" sm="4">
                <v-sheet class="ma-2 pa-2">
                    <a class="" :href="post.redirect" target="_blank">
                        <v-card :text="post.like"></v-card>
                        <v-img aspect-ratio="16/9" cover :src="post.url" alt="url post"></v-img>
                    </a>
                </v-sheet>
            </v-col>
        </v-row>
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

<style></style>