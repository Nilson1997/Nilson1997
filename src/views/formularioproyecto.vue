<template>
    <div>

        <h1>Formulario de Proyecto</h1>

    <b-container fluid>
    <form>
      <b-row class="my-1" v-for="type in types" :key="type">
        <b-col md="10">
          <label :for="`type-${type}`"> <code>{{ type }}</code>:</label>
        </b-col>
        <b-col sm="4">
          <b-form-input :id="`type-${type}`" :type="type" :state="true"></b-form-input>
        </b-col>
      </b-row>
    </form>
    </b-container>
    </div>
  </template>
  
  <script>
    export default {
      data() {
        return {
          types: [
            'Nombre',
            'Categoria',
            'Descripcion',
            'Foto',
            'Instructor',
            'Codigo Fuente',
            'Url o documento' 
          ]
        }
      }
    }
  </script>