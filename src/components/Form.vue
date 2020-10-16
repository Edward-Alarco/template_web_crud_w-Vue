<template>
    <div class="container-form">
    <v-container>
        <v-row class="row-custom">
            <v-col cols="6" class="col-custom2">
                <v-img src="../assets/imgForm.jpg"></v-img>
            </v-col>
            <v-col cols="6" class="col-custom">
                <h4 v-text="title"></h4>
                <v-form>
                    <v-text-field dark v-model="nombre" label="Name"></v-text-field>
                    <v-text-field dark v-model="email" label="Email"></v-text-field>
                    <v-textarea no-resize dark label="Message" v-model="message"></v-textarea>
                    <v-btn block color="#4E4E4E" dark tile>{{btnTxt}}</v-btn>
                </v-form>
            </v-col>
        </v-row>
    </v-container>
    </div>
</template>

<script>
export default {
    name: 'Form',
    data(){
        return{
            btnTxt: 'Enviar',
            title: 'Contact',
            nombre: '',
            email: '',
            message: '',
        }
    }
}
</script>

<style>
.row-custom{
    padding: 100px;
}
div.container-form{
    background-color: rgba(105, 105, 105, 0.5);
    width: 100%;
    margin: 80px 0 0 0;
}
div.col-custom{
    padding: 25px 50px;
    background-color: #696969;
}
.col-custom h4{
    color: #fff;
    font-size: 30px;
    font-weight: 200;
}
div.col-custom2{
    padding: 0;
}
div.col-custom2 .v-image{
    vertical-align: top;
}
.theme--light.v-image{
    vertical-align: top;
}
</style>