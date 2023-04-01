<template >
    <div>
        <header>
            <Nabvar></Nabvar>
        </header>
        <div class="container">
            <div class="row">
                <div class="mt-4">
                    <h4>Left and Right (or Start and End)</h4>
                    <b-card >
                        <b-card-text>

                            <b-img left src="https://picsum.photos/1024/400/?image=41"  alt="Circle image"></b-img>
                            {{ proyecto.descripcion }}
                        </b-card-text>
                    </b-card>
                </div>
            </div>
        </div>
    </div>
</template >
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
            proyecto: {
                id:null,
                nombre:null,
                descripcion:null
            }
        }
    },
    methods:{
        async verProyecto (){
        let id = this.$route.params.id
        await axios.get("http://127.0.0.1:8000/api/proyecto/"+id+"/").then(response=>{
            this.proyecto.id=response.data.id
            this.proyecto.nombre=response.data.nombre_proyecto
            this.proyecto.descripcion=response.data.descripcion

            });
        }   
    },
    async mounted(){
        await this.verProyecto()
    }
}
</script>
<style>

</style>