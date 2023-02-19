<script setup>
    import { RouterLink, RouterView } from 'vue-router'
    import { ref } from 'vue'
    const pokemons = [
        'sobble',
        'scatterbug',
        'combee',
        'oshawott',
        'purugly',
        'espeon&Deoxys GX',
        'toxapex',
        'eneporter',
        'tyranitar',
        'dhelmise',
        'meowth',
        'beartic',
        'pikachu&Zekrom GX',
        'coalossal'
    ]
    const searchTerm = ref('')
    function search() {
        if (pokemons.includes(searchTerm.value.toLowerCase())) {
            alert('Den finns i lager')
        } else {
            alert('Den finns tyvärr inte i lager')
        }
    }
</script>

<template>
    <nav class="navbar navbar-expand-lg navbar-light bg-light fixed-top">
        <div class="container-fluid">
            <RouterLink class="navbar-brand" to="/">Home</RouterLink>
            <button
                class="navbar-toggler"
                type="button"
                data-bs-toggle="collapse"
                data-bs-target="#navbarTogglerDemo02"
                aria-controls="navbarTogglerDemo02"
                aria-expanded="false"
                aria-label="Toggle navigation"
            >
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarTogglerDemo02">
                <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                    <li class="nav-item">
                        <RouterLink
                            to="/köp"
                            class="nav-link active"
                            aria-current="page"
                            href="#"
                            >Köp</RouterLink
                        >
                    </li>
                </ul>
                <form class="d-flex" @submit.prevent="search">
                    <input
                        class="form-control me-2"
                        type="search"
                        placeholder="Sök i lager"
                        aria-label="Search"
                        v-model="searchTerm"
                    />
                    <button class="btn btn-outline-success" type="submit">
                        Sök
                    </button>
                </form>
            </div>
        </div>
    </nav>
    <RouterView />
</template>

<style scoped></style>
