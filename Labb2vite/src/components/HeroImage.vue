<script>
export default {
    data(){
        return {rub: 3}
    }
}
</script>

<template>
    <!-- Hero -->
    <div
      class="hero-image w-100 vh-100 d-flex justify-content-center algin-items-center"
    >
      <div>
        <h1 class="rubrik" :class="{ n: rub}">PokéShop</h1>
      </div>
    </div>
</template>
<style>
.hero-image {
    background-image: linear-gradient(rgba(0, 0, 0, 0.2), rgba(0, 0, 0, 0.3)),
        url(src/assets/imges/photo-1647892591703-4552c35a58e7.jpg);
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    position: relative;
    align-items: center;
    justify-content: center;
    position: relative;
    text-align: center;
}
h1{
    padding-bottom: 40vh;
    font-size: 6rem;
}
.n{
    color: rgb(9, 9, 9)
}
@media screen and (max-width: 600px) {
    h1{
        font-size: 4rem;
    }
}
</style>
