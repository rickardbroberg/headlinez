<template>
    
    <div class="container container--fluid">
        <div class="layout row wrap">
          
          <div class="flex my-2 text-left xs12">
            <h1>Prislista</h1> 
            <p class="feed-subheading mt-4"><span>Headlinez är en kontantfri salong, det är av säkerhetsskäl somm vi beslutat detta. Prislistan visar priser på de vanligaste behandlingarna, för ett mer exakt pris är du välkommen till oss för en kort konsultation som är kostnadsfri.<br><br></span></p>

            <div class="my-5 xs12 align-center hidden-md-and-down"><hr role="separator" aria-orientation="horizontal" class="grey feed-border v-divider theme--light"></div>
            

            <v-row no-gutters>
              <v-col
                cols="12"
                sm="4"
              >
                <v-card
                  class="ma-3 pa-6"
                  max-width="400"
                >
                  <v-simple-table class="theme--light">
                    <template v-slot:default>
                      <thead>
                        <tr>
                          <th class="text-left">Klippning</th>
                          <th class="text-left">Pris</th>
                        </tr>
                      </thead>
                      <tbody>
                        <tr v-for="item in klippningar" :key="item.name">
                          <td>{{ item.name }}</td>
                          <td>{{ item.price }}</td>
                        </tr>
                      </tbody>
                    </template>
                  </v-simple-table>
                </v-card>
              </v-col>

              <v-col
                cols="12"
                sm="4"
              >
                <v-card
                  class=" ma-3 pa-6"
                  max-width="400"
                >
                  <v-simple-table class="theme--light">
                    <template v-slot:default>
                      <thead>
                        <tr>
                          <th class="text-left">Färning</th>
                          <th class="text-left">Pris</th>
                        </tr>
                      </thead>
                      <tbody>
                        <tr v-for="item in fargningar" :key="item.name">
                          <td>{{ item.name }}</td>
                          <td>{{ item.price }}</td>
                        </tr>
                      </tbody>
                    </template>
                  </v-simple-table>
                </v-card>
              </v-col>
            </v-row>

          </div>
          

      </div>
    </div>
    

     
      
  
</template>

<script>
import Vue from 'vue'
import Vuetify from 'vuetify'
import 'vuetify/dist/vuetify.min.css'

Vue.use(Vuetify)

export default {
  data: () => ({
    
    klippningar: [
      {
        name: 'Kort hår',
        price: 380,
      },
      {
        name: 'Långt hår',
        price: 450,
      },
      {
        name: 'Studenter',
        price: '350/380',
      },
      {
        name: 'Pensionärer',
        price: 350,
      },
      {
        name: 'Luggklippning',
        price: 100,
      },
      {
        name: 'Barnklippning upp till 10 år',
        price: 300,
      },
      {
        name: 'Rakning',
        price: 200,
      },
      {
        name: 'Tvätt och extra fin föning',
        price: 300,
      }
    ],
    fargningar: [
      {
        name: 'Kort hår',
        price: 690,
      },
      {
        name: 'Mellanlångt',
        price: 890,
      },
      {
        name: 'Långt hår',
        price: 1090,
      },
      {
        name: 'Extra färgtillägg',
        price: 300,
      },
      {
        name: 'Färgning (Herr( ink. klippning',
        price: 690,
      }
    ],
  }),
  components: {
    
  }
}
</script>

<style>
  

th{
  font-weight: 700;
  color: #000;
}

.layout .flex {
    padding: 12px;
}


@media only screen and (min-width: 768px) {

  
  
  

}
</style>
