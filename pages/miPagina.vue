<template>
  <div><p>mi pagina</p>
    <div>
        <v-btn @click="obtenerCotizacion()" color="primary">Cotización</v-btn>    
      </div>

    <p> {{ datosjson }}</p>
    
  </div>
</template>

<script>


export default {
  name: 'miPagina',
  data () {
    return {
      datosjson:[],
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js'
    }
  },
  methods: {
      obtenerCotizacion() {       
      alert("entra en la funcion de cotizacion");
      //this.$http.get('https://api.coincap.io/v2/assets')      
      this.$axios.get('https://jsonplaceholder.typicode.com/users')      
      .then(response => {
        // Manejar la respuesta
        alert("llega la respuesta")
        this.datosjson = response.data;
        console.log("la data es: " + response.data);
      })
      .catch(error => {
        // Manejar errores
        alert('Error al obtener datos:', error);
      });
      
      
       
    },
    obtenerCotizacion2()
      {
       
      },
  },
  
}
</script>
