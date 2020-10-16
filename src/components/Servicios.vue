<template>
    <v-container>
        <h3 class="display-3 d-block text-center text-uppercase" v-text="title"></h3>
        <v-row>
            <v-col cols="6" sm="6" md="4" v-for="icon in icons" :key="icon" class="pa-5">
                <v-card class="d-flex justify-center align-center text-center" color="rgba(0,0,0,0.2)" dark>
                    <v-icon class="d-block">{{icon.nombre}}</v-icon>
                </v-card>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
export default {
    name: 'Servicios',
    data(){
        return{
            title: 'Services',
            icons: [
                {tec: 'HTML5', nombre: 'fab fa-html5'},
                {tec: 'CSS3', nombre: 'fab fa-css3-alt'},
                {tec: 'JavaScript', nombre: 'fab fa-js'},
                {tec: 'Bootstrap', nombre: 'fab fa-bootstrap'},
                {tec: 'VueJs', nombre: 'fab fa-vuejs'},
                {tec: 'Angular', nombre: 'fab fa-angular'}
            ]
        }
    }
}
</script>

<style>
h3{
    color: #fff;
    margin-top: 50px;
    margin-bottom: 50px;
    font-weight: 600;
}
.v-sheet.v-card:not(.v-sheet--outlined){
    height: 355px;
    transform: scale(1);
    transition: all .25s ease-in-out;
}
.v-sheet.v-card:not(.v-sheet--outlined):hover{
    transform: scale(0.975);
}
.v-card>.v-card__progress+:not(.v-btn):not(.v-chip), .v-card>:first-child:not(.v-btn):not(.v-chip){
    font-size: 150px;
}
</style>