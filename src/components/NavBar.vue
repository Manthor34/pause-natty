<template>
    <nav class="elevation-12 d-none d-md-flex">
        <img src="../assets/logo-pause-natty.webp" alt="">
        <a href="#section-concept">Concept</a>
        <a href="#section-valeurs">Valeurs</a>
        <a href="#section-calories">Compteur de calories</a>
    </nav>
</template>

<script>
export default {

}
</script>

<style>
nav {
    display: flex;
    justify-content: center;
    gap: 10%;
    align-items: center;
    background-color: white;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    padding: 10px 20px;
}

nav a {
    color: #333;
    text-decoration: none;
    font-weight: bold;
    font-size: 30px;
    margin-right: 20px;
    padding: 5px 10px;
    transition: all 0.2s ease-in-out;
}

nav a:hover {
    color: #000;
    font-weight: bold;
    padding: 5px 10px;
    border-radius: 10px;
}

nav a:not(:hover) {
    opacity: 0.5;
}

nav img {
    width: 128px;
}
</style>