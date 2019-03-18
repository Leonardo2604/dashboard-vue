<template>
    <v-app>
        <!-- mobile-break-point="768" -->
        <v-navigation-drawer app v-model="drawer">
            <v-list>
                <v-list-tile avatar>
                    <v-list-tile-avatar>
                        <img src="https://randomuser.me/api/portraits/men/85.jpg">
                    </v-list-tile-avatar>

                    <v-list-tile-content>
                        <v-list-tile-title>Leonardo R.</v-list-tile-title>
                    </v-list-tile-content>
                </v-list-tile>
                <v-list-tile @click="goTo({name: 'home'})">
                    <v-list-tile-action>
                        <v-icon>dashboard</v-icon>
                    </v-list-tile-action>
                    <v-list-tile-title>Dashboard</v-list-tile-title>
                </v-list-tile>

                <v-list-group prepend-icon="assignment" no-action>
                    <template v-slot:activator>
                        <v-list-tile>
                            <v-list-tile-title>Cadastro</v-list-tile-title>
                        </v-list-tile>
                    </template>
                    <v-list-tile v-for="(item, i) in register" :key="i" @click="()=> null">
                        <v-list-tile-title v-text="item"></v-list-tile-title>
                    </v-list-tile>
                </v-list-group>

                <v-list-group prepend-icon="autorenew" no-action>
                    <template v-slot:activator>
                        <v-list-tile>
                            <v-list-tile-title>Movimentação</v-list-tile-title>
                        </v-list-tile>
                    </template>
                    <v-list-tile v-for="(item, i) in movimentation" :key="i" @click="()=> null">
                        <v-list-tile-title v-text="item"></v-list-tile-title>
                    </v-list-tile>
                </v-list-group>

                <v-list-group prepend-icon="verified_user" no-action>
                    <template v-slot:activator>
                        <v-list-tile>
                            <v-list-tile-title>Segurança</v-list-tile-title>
                        </v-list-tile>
                    </template>
                    <v-list-tile v-for="(item, i) in security" :key="i" @click="()=> null">
                        <v-list-tile-title v-text="item"></v-list-tile-title>
                    </v-list-tile>
                </v-list-group>

                <v-list-tile @click="()=> null">
                    <v-list-tile-action>
                        <v-icon>exit_to_app</v-icon>
                    </v-list-tile-action>
                    <v-list-tile-title>Sair</v-list-tile-title>
                </v-list-tile>
            </v-list>
        </v-navigation-drawer>
        <v-toolbar app color="primary" dark>
            <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
            <v-toolbar-title>Dashboard</v-toolbar-title>

            <v-spacer></v-spacer>

            <v-menu bottom left>
                <template v-slot:activator="{ on }">
                    <v-btn icon v-on="on">
                        <v-icon>more_vert</v-icon>
                    </v-btn>
                </template>

                <v-list>
                    <v-list-tile @click="() => null">
                        <v-list-tile-content>
                            <v-list-tile-title>Meus dados</v-list-tile-title>
                        </v-list-tile-content>
                    </v-list-tile>

                    <v-list-tile @click="() => null">
                        <v-list-tile-content>
                            <v-list-tile-title>Configurações</v-list-tile-title>
                        </v-list-tile-content>
                        <v-list-tile-action>
                            <v-icon>settings</v-icon>
                        </v-list-tile-action>
                    </v-list-tile>

                    <v-list-tile @click="goTo({name: 'about'})">
                        <v-list-tile-content>
                            <v-list-tile-title>Sobre</v-list-tile-title>
                        </v-list-tile-content>
                        <v-list-tile-action>
                            <v-icon>help_outline</v-icon>
                        </v-list-tile-action>
                    </v-list-tile>
                </v-list>
            </v-menu>
        </v-toolbar>
        <v-content>
            <v-container fluid>
                <v-fade-transition mode="out-in">
                    <router-view></router-view>
                </v-fade-transition>
            </v-container>
        </v-content>
        <v-footer app>
            <v-layout justify-center>
                <div>&copy; {{ new Date().getFullYear() }} — <strong>Leonardo Rangel dos Santos</strong></div>
            </v-layout>
        </v-footer>
    </v-app>
</template>

<script>
    export default {
        name: "App",
        components: {

        },
        methods: {
            goTo: function(nameRouter) {
                this.$router.push(nameRouter);
            }
        },
        data() {
            return {
                drawer: false,
                register: [
                    'Produto',
                    'Categoria',
                    'Setores',
                    'Fornecedor'
                ],
                movimentation: [
                    'Compras',
                    'Vendas',
                    'Ordens de Serviço'
                ],
                security: [
                    'Usuários',
                    'Grupos',
                    'Configuração de aplicações',
                    'Logs'
                ]
            };
        }
    };
</script>