<template>
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
                    <v-textarea dark label="Message" v-model="message"></v-textarea>
                </v-form>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
export default {
    name: 'Form',
    data(){
        return{
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
    background-color: rgba(105, 105, 105, 0.5);
}
.col-custom{
    padding: 40px;
    background-color: #696969;
}
.col-custom h4{
    color: #fff;
    font-size: 30px;
    font-weight: 200;
}
.col-custom2{
    padding: 0;
}
</style>