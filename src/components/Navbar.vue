<template>
    <nav>
        <v-app-bar app flat class="grey--text">
            <v-app-bar-nav-icon @click="drawer=!drawer"></v-app-bar-nav-icon>
            <v-app-bar-title>
                Le Polymag Orléans
            </v-app-bar-title>
        </v-app-bar>
        <v-navigation-drawer v-model="drawer" app class="deep-purple">
            <v-list>
                <v-list-item v-for="link in links" :key="link.text" router :to="link.route">
                    <v-list-item-action>
                        <v-icon class="white--text"> {{ link.icon }} </v-icon>
                    </v-list-item-action>
                    <v-list-item-content class="white--text"> {{ link.text }} </v-list-item-content>
                </v-list-item>

            </v-list>
        </v-navigation-drawer>
    </nav>
</template>

<script>
export default {
    data(){
        return {
            drawer: false,
            links: [
                { icon: 'mdi-view-dashboard', text: 'Accueil', route: '/'},
                { icon: 'mdi-account-group', text: "L'équipe", route: '/team'},
                { icon: 'mdi-help', text: 'À propos', route:'/about'},
            ]
        }
    }
    
}
</script>