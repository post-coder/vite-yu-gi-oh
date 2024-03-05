<script>
export default {
    name: 'AppLoader',

}
</script>

<template>
    <div id="loader-wrapper">
        <div class="img-wrapper">
            <img src="/img/loader.png" alt="loader">
        </div>
    </div>
</template>

<style lang="scss" scoped>
#loader-wrapper {
    position: fixed;
    left: 0;
    top: 0;

    width: 100%;
    height: 100%;

    background-color: black;
}

.img-wrapper {
    position: fixed;

    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}

img {
    animation: ruota 1s linear infinite;
}

@keyframes ruota {
    0% {
        transform: rotate(0deg);
    }

    100% {
        transform: rotate(360deg);
    }
}

</style>
