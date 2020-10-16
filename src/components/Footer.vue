<template>
    <div>
        <v-container>
            <div class="text-center text-footer pt-5">
                <h5>{{title}}</h5>
                <div v-for="n in iconos" :key="n" class="d-inline">
                    <v-btn icon target="_blank" :href="n.url"><v-icon class="mx-2 my-2 v-icon">{{n.icn}}</v-icon></v-btn>
                </div>
                <p>&copy;{{credits}}</p>
            </div>
        </v-container>
    </div>
</template>

<script>
export default {
    name: 'Footer',
    data(){
        return{
            title: 'COMPANY’S NAME',
            credits: 'Todos los Derechos Reservados',
            iconos: [
                {icn: 'fab fa-instagram', url: 'https://www.instagram.com/edward_alarco/'},
                {icn: 'fab fa-facebook', url: 'https://www.facebook.com/edward.david.alarco'},
                {icn: 'fab fa-github', url: 'https://github.com/Edward-Alarco'},
            ]
        }
    }
}
</script>

<style>
.v-icon.v-icon,.theme--light.v-icon,.v-application .mx-2{
    color: white !important;
}
.text-footer,.v-icon{
    color: #fff;
}
.text-footer h5{
    font-size: 30px;
    font-weight: 100;
}
.text-footer p{
    margin-top: 30px;
    color: rgba(255, 255, 255, 0.1);
}
.v-application p{
    margin-bottom: 0;
}
</style>