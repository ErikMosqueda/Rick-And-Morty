<script>
    import axios from 'axios'
    let API_URL = `https://rickandmortyapi.com/api/character`
    export default {
      data() {
        return {
          info: [],
          personajes: [],
          personajesEncontrados: [],
          buscar: '',
          cont:2,
          contador:2
        }
      },
      computed: {
 
  },
      mounted() {
        axios.get(API_URL)
          .then((response) => {
            this.info = response.data.info;
            this.personajes = response.data.results;
          })
      },
      methods: {
        pag(num) {
          //API_URL='https://rickandmortyapi.com/api/character/?page='+num
          console.log(API_URL)
          axios.get(API_URL)
          .then((response) => {
            console.log(response.config)
            this.info = response.data.info;
            this.personajes = response.data.results;
          })
           this.cont++ 
        },
        sumar(contador){
          this.contador++
          API_URL='https://rickandmortyapi.com/api/character/?page='+contador
          console.log(API_URL)
          axios.get(API_URL)
          .then((response) => {
            console.log(response.config)
            this.info = response.data.info;
            this.personajes = response.data.results;
            console.log(info.next);
          })
          

        },
        restar(contador){
          
          API_URL='https://rickandmortyapi.com/api/character/?page='+contador
          console.log(API_URL)
          axios.get(API_URL)
          .then((response) => {
            console.log(response.config)
            this.info = response.data.info;
            this.personajes = response.data.results;
            console.log(info.prev);
          })
          

        },
        buscador(buscar){
          API_URL='https://rickandmortyapi.com/api/character/?name='+buscar
          console.log(API_URL)
          axios.get(API_URL)
          .then((response) => {
            console.log(response.config)
            this.info = response.data.info;
            this.personajesEncontrados = response.data.results;
          })
          
        

        }
      },
    }
    </script>
    
    <template  >
            <!-- INICIAR CON EL BUSCADOR -->
        <div class="flex justify-center">
          <div class="mt-1 mr-2 font-bold text-xl">Buscar:</div>
          
          <div class=" mr-3 mb-3">
            <input type="text" v-model="buscar" class="form-control rounded-lg px-3 py-1" placeholder="Ejemplo: Rick"/>
          </div>
          
          <div class="w-6 mt-1 hover:-translate-y-1 hover:scale-105 " >
            <button class="" @click="buscador(buscar)"> <RouterLink to="">
            <img class="rounded-lg mb-3 " src='../assets/lupa.png' alt="">
            </RouterLink>
            </button>
          </div>
        </div>


          <!-- CAMBIAR DE PAGINAS -->
          <div class="">
             <div class=" justify-between flex ml-3 mr-3 mb-3" >
                <div class="hover:-translate-y-1 hover:scale-100" v-if="contador>=3 && contador<=42">
                  <button @click="restar(contador)" class=" rounded-lg border-2 border-lime-500 bg-slate-200 shadow-xl shadow-lime-200/50 px-3 py-2 "> Anterior </button>
                </div>
                
                 <div class="hover:-translate-y-1 hover:scale-100">
                  
                </div>
                
                <div class="hover:-translate-y-1 hover:scale-100" v-if="contador>=1 && contador<=42">
                  <button @click="sumar(contador)" class=" rounded-lg border-2 border-lime-500 shadow-xl bg-slate-200 shadow-lime-200/50 px-3 py-2"> Siguiente</button>
                </div>

               
                <!-- P??gina: {{ cont  }} -->
                
              </div>
          </div>
        

        <!-- HACER EL RECORRIDO E IMPRESION DE LOS PERSONAJES  -->
        <div v-if="buscar.length !== 0" v-for="p in personajesEncontrados" class= "border-solid border-2 rounded-lg border-current mb-6 ml-6 mr-6">
          <div>
              <h2 class="font-bold text-xl text-center">
                  {{p.id}}.- 
                  {{p.name}}
              </h2>
  
          </div>

          <div class="justify-start ml-3 mb-5">
              Fecha de creaci??n: {{p.created}} <br>
              Estado actual: {{p.status}}  <br>
              Tipo de especie: {{p.species}}  <br>
          </div>


      </div>


        <div v-else="" v-for="p in personajes" class= "border-solid border-2 rounded-lg border-current mb-6 ml-6 mr-6">
            <div>
                <h2 class="font-bold text-xl text-center">
                    {{p.id}}.- 
                    {{p.name}}
                </h2>
    
            </div>

            <div class="justify-start ml-3 mb-5">
                Fecha de creaci??n: {{p.created}} <br>
                Estado actual: {{p.status}}  <br>
                Tipo de especie: {{p.species}}  <br>
            </div>


        </div>
        <!-- <div class="grid grid-cols-4 gap-4" v-for="p in personajes">
            <div class="card">01
                <a >{{ p.name }} id:{{ p.id }}</a> 
            </div>
             ... -->
           <!--  <div>09</div>
          </div> --> -->
      
    </template>