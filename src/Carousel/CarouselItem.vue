<template>
    <transition name="slide-in">
        <div v-show="currentSlide === index">
            <img :src="movie.image">
        </div>
    </transition>
</template>

<script>
    export default {
        props: ["movie", "currentSlide", "index"]
    }
</script>

<style scoped>

    div {
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        width: 300px;
        height: 400px;
    }

    img {
        object-fit: cover;
        object-position: top;
    }

    .slide-in-enter-active,
    .slide-in-leave-active {
        transition: all 1s ease-in-out;
    }

    .slide-in-enter-from {
        transform: translateX(-100%)
    }

    .slide-in-leave-to {
        transform: translateX(100%)
    }

</style>