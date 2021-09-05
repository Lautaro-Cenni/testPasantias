<template>
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
        <nuxt-link class="navbar-brand" to="/">HOME</nuxt-link>
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarColor01" aria-controls="navbarColor01" aria-expanded="true" aria-label="Toggle navigation" data-v-ed554c1c>
        <span class="navbar-toggler-icon"></span>
        </button>

        <div class="collapse navbar-collapse" id="navbarColor01">
            <ul class="navbar-nav mr-auto">
                <li class="nav-item active">
                <nuxt-link class="nav-link" to="/posts">VEHÍCULOS</nuxt-link>
                </li>
                <li class="nav-item">
                <nuxt-link class="nav-link" to="/">DESCUBRÍ NISSAN</nuxt-link>
                </li>
            </ul>
        </div>
    </nav>
</template>

<script>

export default {
        name: 'Nav'
    }
</script>

<style>

.navbar-dark .navbar-nav .nav-link{
    color:#ccc6c6;
    margin-left: 1rem;
}
.navbar-dark .navbar-brand {
    color:#CE1212;
    margin-left: 1rem;
}
.navbar-dark .navbar-brand:focus{
    color:#CE1212;
}
.navbar-dark .navbar-brand:hover{
    color:white;
}
.navbar-dark .navbar-collapse{
    margin-left: 1rem;
}
</style>