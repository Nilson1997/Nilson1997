<template>
    <div class="container ">
        <div class="row">
            <H1>Formulario</H1>
            <br>
            <b-col sm="4" md="7">
            <h5>Nombre del Proyecto</h5>
            </b-col>
            <b-form-input v-model="text" placeholder=""></b-form-input>
            <br>
            <h5>Categoria</h5>
            <b-form-input v-model="text" placeholder=""></b-form-input>
            <br>
            <h5>Descripcion</h5>
            <b-form-input v-model="text" placeholder=""></b-form-input>
            <br>
            <h5>Foto</h5>
            <b-form-file v-model="File" placeholder=""></b-form-file>
            <br>
            <h5>Instructor</h5>
            <b-form-input v-model="text" placeholder=""></b-form-input>
            <br>
            <h5>Codigo fuente</h5>
            <b-form-input v-model="text" placeholder=""></b-form-input>
            <br>
            <h5>Documento</h5>
            <b-form-file v-model="File" placeholder=""></b-form-file>
            <br>
            <h5>Descripcion de entrega</h5>
            <b-form-textarea v-model="text" placeholder="Descripcion"></b-form-textarea>
            <div class="row justify-content-around">
                <div class="col-1">
                    <b-button type="Enviar" variant="primary">Enviar</b-button>     
                </div>
                <div class="col-1">
                    <b-button type="Cancelar" variant="danger">Cancelar</b-button>     

                </div>
            </div>
 
            <div class="mt-2"></div>
        </div>
    </div>
  </template>
  
  <script>
    export default {
      data() {
        return {

        }
      }
    }
  </script>
  <style>
.margen{
    margin: 10px;
    color: black;
}
</style>