<template>
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
        <div class="container-fluid">
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav"
                aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarNav">
                <ul class="navbar-nav">
                    <li class="nav-item">
                        <nuxt-link to="/" class="nav-link">Home</nuxt-link>
                    </li>
                    <li class="nav-item">
                        <nuxt-link to="/about" class="nav-link">About</nuxt-link>
                    </li>
                    <li class="nav-item">
                        <nuxt-link to="/gallery" class="nav-link">Gallery</nuxt-link>
                    </li>
                    <li class="nav-item">
                        <nuxt-link to="/weather" class="nav-link">Weather</nuxt-link>
                    </li>
                </ul>
            </div>
        </div>
    </nav>
</template>

<script lang="js">
export default {
  name: 'navBar',
}
</script>
