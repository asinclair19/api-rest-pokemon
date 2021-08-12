<template>
    <div class="mb-4">
        <b-navbar toggleable="lg" type="dark" variant="info">
            <b-navbar-brand to="/">
                <img src="../static/pokeapi_img.png" alt="api pokeapi" width="100px">
            </b-navbar-brand>

            <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

            <b-collapse id="nav-collapse" is-nav>
                <b-navbar-nav>
                    <b-nav-item to="/">Home</b-nav-item>
                    <b-nav-item to="/saved">Saved</b-nav-item>
                </b-navbar-nav>
            <!-- Right aligned nav items -->
            </b-collapse>
        </b-navbar>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>

</style>