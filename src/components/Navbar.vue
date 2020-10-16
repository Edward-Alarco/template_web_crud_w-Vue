<template>
    <div>
        <v-toolbar dark flat color="#222222">
            <v-toolbar-title>
                <h3>{{title}}</h3>
            </v-toolbar-title>
            <v-spacer></v-spacer>
            <v-icon class="mr-5">{{fa}}facebook</v-icon>
            <v-icon class="mr-3">{{fa}}instagram</v-icon>
        </v-toolbar>
    </div>
</template>

<script>
export default {
    name: 'Navbar',
    data(){
        return{
            title: 'Company',
            fa: 'fab fa-',
        }
    }
}
</script>