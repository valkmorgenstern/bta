<template xmlns:v-slot="http://www.w3.org/1999/XSL/Transform">
    <v-card class="overflow-hidden">
        <v-app-bar
            absolute
            color="#43a047"
            dark
            shrink-on-scroll
            prominent
            src="https://picsum.photos/1920/1080?random"
            fade-img-on-scroll
            scroll-target="#scrolling-techniques-5"
            scroll-threshold="500">
            <template v-slot:img="{ props }">
                <v-img
                    v-bind="props"
                    gradient="to top right, rgba(55,236,186,.7), rgba(25,32,72,.7)"
                ></v-img>
            </template>

            <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>

            <v-toolbar-title>Приложение</v-toolbar-title>

            <div class="flex-grow-1"></div>

            <modal-registration></modal-registration>
        </v-app-bar>
        <v-sheet
            id="scrolling-techniques-5"
            class="overflow-y-auto">
            <!--max-height="600"-->
        <!--&gt;-->
            <v-container style="height: 1500px;"></v-container>
        </v-sheet>
        <!--<v-navigation-drawer-->
            <!--app-->
            <!--temporary=""-->
            <!--v-model="drawer">-->
            <!--<v-list>-->
                <!--<v-list-tile-->
                    <!--v-for="link of links"-->
                    <!--:key="link.title"-->
                    <!--:to="link.url"-->
                    <!--@click="logout(link.title)">-->
                    <!--<v-list-tile-action>-->
                        <!--<v-icon>{{link.icon}}</v-icon>-->
                    <!--</v-list-tile-action>-->
                    <!--<v-list-tile-content>-->
                        <!--<v-list-tile-title v-text="link.title"></v-list-tile-title>-->
                    <!--</v-list-tile-content>-->
                <!--</v-list-tile>-->
            <!--</v-list>-->
        <!--</v-navigation-drawer>-->
    </v-card>

</template>

<script>
    import Registration from '../../components/modals/Registration'

    export default {
        name: "MainNavbar",
        props: ['drawer'],
        components: {
            ModalRegistration: Registration
        }
    }
</script>

<style scoped>

</style>
