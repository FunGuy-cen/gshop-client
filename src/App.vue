<template>
    <div id="app">
        <router-view />
        <!-- $route ????-->
        <FooterGuide v-show="$route.meta.showFooter" />
    </div>
</template>

<script>
import FooterGuide from "./components/FooterGuide/FooterGuide";
import { reqFoodTypes } from './api'

export default {

    async mounted() {
        const result = await reqFoodTypes()
        console.log(result)
    },

    components: {
        FooterGuide
    }
}
</script>

<style lang="stylus" rel="stylesheet/stylus">
#app
    width: 100%
    height: 100%
    background: #ffffff
</style>
