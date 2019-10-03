<template>
    <main-navbar :drawer="drawer"></main-navbar>
</template>

<script>
    import MainNavbar from '../../components/navbars/MainNavbar'
    export default {
        name: "NotAuth",
        data () {
            return {
                drawer: false
            }
        },
        components: {
            MainNavbar
        }
    }
</script>

<style scoped>

</style>
