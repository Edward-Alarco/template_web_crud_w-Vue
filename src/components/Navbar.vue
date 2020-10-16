<template>
    <div>
        <v-toolbar dark flat color="#222222">
            <v-toolbar-title>
                <h3>{{title}}</h3>
            </v-toolbar-title>
            <v-spacer></v-spacer>
            <div class="mr-2">
                <v-btn icon target="_blank" href="https://www.facebook.com/edward.david.alarco"><v-icon>{{fa}}facebook</v-icon></v-btn>
                <v-btn icon target="_blank" href="https://www.instagram.com/edward_alarco/"><v-icon>{{fa}}instagram</v-icon></v-btn>
                <v-btn icon target="_blank" href="https://github.com/Edward-Alarco"><v-icon>{{fa}}github</v-icon></v-btn>
            </div>
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