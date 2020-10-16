<template>
<div class="crud">
  <v-container grid-list-xl>
    <v-btn icon class="btnhome mb-5" to="/"><v-icon class="iconohome">fas fa-home</v-icon></v-btn>
    <v-layout row wrap>
      <v-flex md6>
        <v-card class="mb-3" v-for="(item, index) in listaTareas" :key="index">
          <v-card-text>
            <v-chip class="mb-4" color="pink" label text-color="white">
              <v-icon left> mdi-label </v-icon>{{ item.titulo }}
            </v-chip>
            <p>
              {{ item.descripcion }}
            </p>
            <v-btn color="warning" class="mr-3" @click="editarTarea(index)">Editar</v-btn>
            <v-btn color="error" @click="eliminarTarea(item.id)">Eliminar</v-btn>

          </v-card-text>
        </v-card>

        <!-- <v-card class="mb-3">
          <v-card-text>
            <v-chip class="mb-4" color="pink" label text-color="white">
              <v-icon left> mdi-label </v-icon>Tarea2
            </v-chip>
            <p>
              Lorem ipsum dolor sit amet consectetur adipisicing elit.
              Blanditiis perspiciatis ullam eligendi labore earum repudiandae
              veritatis mollitia officiis saepe voluptatem! Autem iure vero
              nihil obcaecati rerum itaque deleniti culpa sed.
            </p>
            <v-btn color="warning" class="mr-3">Editar</v-btn>
            <v-btn color="error">Eliminar</v-btn>
          </v-card-text>
        </v-card> -->
      </v-flex>

      <v-flex v-if="formAgregar" md6>
        <v-card class="mb-3 pa-5">
          <v-form @submit.prevent="agregarTarea">
            <v-text-field label="Titulo" v-model="titulo"></v-text-field>
            <v-textarea label="Descripcion" v-model="descripcion"></v-textarea>
            <v-btn block color="success" type="submit">Agregar</v-btn>
          </v-form>
        </v-card>
      </v-flex>

      <v-flex v-if="!formAgregar" md6>
        <v-card class="mb-3 pa-5">
          <v-form @submit.prevent="editarTareaForm">
            <v-text-field label="Titulo" v-model="titulo"></v-text-field>
            <v-textarea label="Descripcion" v-model="descripcion"></v-textarea>
            <v-btn block color="warning" type="submit">Editar</v-btn>
          </v-form>
        </v-card>
      </v-flex>
    </v-layout>

    <v-snackbar v-model="snackbar" :multi-line="multiLine">
      {{ mensaje }}

      <template v-slot:action="{ attrs }">
        <v-btn color="red" text v-bind="attrs" @click="snackbar = false">
          Close
        </v-btn>
      </template>
    </v-snackbar>

  </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      listaTareas: [
        {
          id: 1,
          titulo: "Tarea1",
          descripcion: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Blanditiis perspiciatis ullam eligendi labore earum repudiandae veritatis mollitia officiis saepe voluptatem! Autem iure vero nihil obcaecati rerum itaque deleniti culpa sed.',
        },
        {
          id: 2,
          titulo: "Tarea2",
          descripcion: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Blanditiis perspiciatis ullam eligendi labore earum repudiandae veritatis mollitia officiis saepe voluptatem! Autem iure vero nihil obcaecati rerum itaque deleniti culpa sed.',
        },
      ],
      titulo: "",
      descripcion: "",
      snackbar : false,
      mensaje: '',
      formAgregar: true,
      indexTarea: ''
    };
  },
  methods: {
    agregarTarea: function () {
      if (this.titulo === "" || this.descripcion === "") {
          this.snackbar = true
          this.mensaje = 'Por favor, llene todos los campos!'
      }else{
          this.listaTareas.push({
              id: Date.now(),
              titulo: this.titulo,
              descripcion: this.descripcion
          })
          this.titulo = ''
          this.descripcion = ''
          this.snackbar = true
          this.mensaje = 'Tarea agregada con exito!'
      }
    },
    eliminarTarea: function(id){
        this.listaTareas = this.listaTareas.filter(e => e.id != id)
        this.snackbar = true
        this.mensaje = 'Tarea eliminada!'
    },
    editarTarea: function(index){
        this.formAgregar = false
        this.titulo = this.listaTareas[index].titulo
        this.descripcion = this.listaTareas[index].descripcion
        this.indexTarea = index
    },
    editarTareaForm: function(){
        if (this.titulo === "" || this.descripcion === "") {
            this.snackbar = true
            this.mensaje = 'Por favor, llene todos los campos!'
        }else{
            this.listaTareas[this.indexTarea].titulo = this.titulo
            this.listaTareas[this.indexTarea].descripcion = this.descripcion
            this.formAgregar = true
            this.titulo = ''
            this.descripcion = ''
            this.snackbar = true
            this.mensaje = 'Se editó la tarea con exito!'
        }
        
    }
  },
};
</script>

<style scoped>
.container{
  margin-top: 50px !important;
}
.btnhome .iconohome{
  color: #000 !important;
}
.v-card>.v-card__progress+:not(.v-btn):not(.v-chip), .v-card>:first-child:not(.v-btn):not(.v-chip){
  font-size: 16px;
}
</style>