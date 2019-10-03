<template xmlns:v-slot="http://www.w3.org/1999/XSL/Transform">
    <v-row justify="center">
        <v-dialog v-model="dialog" persistent max-width="600px">
            <template v-slot:activator="{ on }">
                <div class="flex-grow-1"></div>
                <v-btn icon v-on="on">
                    <v-icon>mdi-login-variant</v-icon>
                </v-btn>
            </template>

            <!--Вот так выглядит окошко-->
            <v-card>
                <v-toolbar dark>
                    <v-toolbar-title>Войти</v-toolbar-title>
                    <div class="flex-grow-1"></div>
                    <v-btn icon dark @click="dialog = false">
                        <v-icon>mdi-close</v-icon>
                    </v-btn>
                </v-toolbar>
                <v-card-text>
                    <v-container>
                        <v-row>
                            <v-col cols="12">
                                <v-text-field label="Email" required></v-text-field>
                            </v-col>
                            <v-col cols="12">
                                <v-text-field label="Password" type="password" required></v-text-field>
                            </v-col>

                        </v-row>
                    </v-container>
                </v-card-text>
                <v-card-actions>
                    <v-col cols="12">
                        <v-row justify="center">
                            <v-col
                                cols="6"
                            >
                                <modal-registration></modal-registration>
                            </v-col>
                            <v-col
                                cols="6"
                            >
                                <v-btn color="black" text @click="dialog = false">Войти</v-btn>
                            </v-col>
                        </v-row>
                    </v-col>
                </v-card-actions>
            </v-card>
        </v-dialog>
    </v-row>
</template>

<script>
    import Registration from '../../components/modals/Registration'

    export default {
        name: "Login",
        data: () => ({
            dialog: false,
        }),
        components: {
            ModalRegistration: Registration
        }
    }
</script>

<style scoped>

</style>
