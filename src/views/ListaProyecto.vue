<template>
    <div>
        <header>
            <Nabvar></Nabvar>
        </header>
    
        <b-nav-form>
            <b-form-input type="text" v-model="searchValue" size="sm" class="mr-sm-2" placeholder="Search" ></b-form-input>
            <b-button size="sm" class="my-2 my-sm-0"  @click="search">Buscar</b-button>
            <div class="listaPyoyecto" v-for="proyecto in proyecto" :key="proyecto.id">
                <h2>{{ proyecto.nombre_proyecto }}</h2>
                <td>
                  <p>{{ proyecto.descripcion }}</p>

                </td>
                <td>
                  
                  <img class="verProyecto" src="../assets/iconos/verProyecto.png" alt="">

                </td>

            </div>
        </b-nav-form> 
      <!-- Agregar más campos del proyecto aquí --> 
        <table>
            <tbody>
                <tr v-for="proyecto in proyectos " :key="proyecto.id" >
                  
                    <td>
                        <div class="container " >
                            <b-card >
                              <b-col md="6">
                                <b-card-img >{{ proyecto.foto }}</b-card-img>
                              </b-col>
                              <b-card-text>
                                <img src="" alt="">
                                <h1>{{ proyecto.id }}</h1>
                                <h3>{{ proyecto.nombre_proyecto}}</h3>
                                <p>{{ proyecto.descripcion }}</p>
                                <img class="position-absolute bottom-0 end-0" src="../assets/iconos/verProyecto.png" alt="" @click="verProyecto(proyecto.id)">
                              </b-card-text>
                            </b-card>
                        </div>
                    </td>    
                </tr>
            </tbody>
        </table>
  
           
    </div>

</template>
<script>
import axios from 'axios'
import Nabvar from '@/components/Nabvar.vue';
export default{
    name:'Lista',
    components:{
       Nabvar
    },
    data(){
        return{
            searchValue: "",
            proyecto: [],
            proyectos: null
        }
    },
    methods:{
        async getProyecto(){
            await axios.get("http://127.0.0.1:8000/api/proyecto/").then(response=>{
            this.proyectos= response.data
      })
    },
    async search() {
      try {
        const response = await axios.get("http://127.0.0.1:8000/buscar_proyectos/", {
          params: {
            search: this.searchValue,
          },
        });
        this.proyecto = response.data;
      } catch (error) {
        console.log(error);
      }
      
    },
    async verProyecto(id){
      this.$router.push('/verProyecto/'+id)
    },


    },
    async mounted() {  
        await this.getProyecto()

    },
        
    
    


}
</script>

<style>

</style> 
