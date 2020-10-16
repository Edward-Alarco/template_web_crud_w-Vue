<template>
    <div>
        <div class="bannerbg d-flex justify-center align-center">
            <div class="text-center">
                <h1 class="font-weight-medium text-uppercase">{{title}}</h1>
                <h3 class="font-weight-regular my-1" v-text="subtitle"></h3>
                <v-btn depressed class="mt-5" to="/crud">{{btntext}}</v-btn>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Banner',
    data(){
        return{
            btntext: 'Ingresar',
            title: "Company's Name",
            subtitle: 'Emotional Phrase'
        }
    }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;500&display=swap');
.v-application .text-center{
    font-family: 'Poppins', sans-serif;
}
.v-application .text-center h1{
    font-size: 100px;
}
.v-application .text-center h3{
    font-size: 60px;
}
div.bannerbg{
    font-family: 'Poppins', sans-serif;
    color: #fff;
    width: 100%;
    height: 89.75vh;
    background: url('../assets/Banner.jpg');
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
}
</style>