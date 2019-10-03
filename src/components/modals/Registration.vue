<template xmlns:v-slot="http://www.w3.org/1999/XSL/Transform">
    <v-row justify="center">
        <v-dialog v-model="dialog" persistent max-width="600px">
            <template v-slot:activator="{ on }">
                <div class="flex-grow-1"></div>
                <v-btn color="blue darken-1" text v-on="on">Создать аккаунт</v-btn>
            </template>

            <!--Вот так выглядит окошко-->
            <v-card>
                <v-toolbar dark>
                    <v-toolbar-title>Создание аккаунта</v-toolbar-title>
                    <div class="flex-grow-1"></div>
                    <v-btn icon dark @click="dialog = false">
                        <v-icon>mdi-close</v-icon>
                    </v-btn>
                </v-toolbar>
                <v-card-text>
                    <v-container>
                        <v-form
                            v-model="valid"
                            ref="form"
                            lazy-validation>
                            <v-row>
                                <v-col cols="12" sm="6" md="4">
                                    <v-text-field
                                        label="Фамилия"
                                        type="text"
                                        v-model="lastName"
                                        :rules="lastNameRules"
                                        required></v-text-field>
                                </v-col>
                                <v-col cols="12" sm="6" md="4">
                                    <v-text-field
                                        label="Имя"
                                        type="text"
                                        v-model="firstName"
                                        :rules="firstNameRules"
                                        required></v-text-field>
                                </v-col>
                                <v-col cols="12" sm="6" md="4">
                                    <v-text-field
                                        label="Отчество"
                                        type="text"
                                        v-model="patronymic"
                                        required
                                    ></v-text-field>
                                </v-col>
                                <v-col cols="12">
                                    <v-text-field
                                        label="Email"
                                        type="email"
                                        v-model="email"
                                        :rules="emailRules"
                                        required></v-text-field>
                                </v-col>
                                <v-col cols="12">
                                    <v-text-field
                                        label="Пароль"
                                        type="password"
                                        v-model="password"
                                        :rules="passwordRules"
                                        required></v-text-field>
                                </v-col>
                                <v-col cols="12">
                                    <v-text-field
                                        label="Подтвердить пароль"
                                        type="password"
                                        v-model="confirmPassword"
                                        :rules="confirmPasswordRules"
                                        required></v-text-field>
                                </v-col>
                            </v-row>
                        </v-form>
                    </v-container>
                </v-card-text>
                <v-card-actions>
                    <div class="flex-grow-1"></div>
                    <v-btn color="blue darken-1" text @click="dialog = false" :disabled="!valid">Создать</v-btn>
                </v-card-actions>
            </v-card>
        </v-dialog>
    </v-row>
</template>

<script>
    export default {
        name: "Registration",
        data() {
            return {
                dialog: false,
                valid: false,
                email: '',
                password: '',
                confirmPassword: '',
                firstName: '',
                lastName: '',
                patronymic: '',
                emailRules: [
                    v => !!v || 'Введите Ваш e-mail',
                    v => /.+@.+/.test(v) || 'E-mail должен быть реальным'
                ],
                passwordRules: [
                    v => !!v || 'Введите пароль',
                    v => (v && v.length >= 4) || 'Пароль должен состоять не менее чем из 6 символов'
                ],
                confirmPasswordRules: [
                    v => !!v || 'Подтвердите пароль',
                    v => v === this.password || 'Пароли должны совпадать'
                ],
                lastNameRules: [
                    v => !!v || 'Введите фамилию',
                    v => (v && v.length > 1) || 'Введите фамилию'
                ],
                firstNameRules: [
                    v => !!v || 'Введите имя',
                    v => (v && v.length > 1) || 'Введите имя'
                ]
            }
        },
    }
</script>

<style scoped>

</style>
