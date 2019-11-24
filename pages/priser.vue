<template>
    
    <div class="container container--fluid">
        <div class="layout row wrap">
          
          <div class="flex my-2 text-left xs12">
            <h1>Prislista</h1> 
            <p class="feed-subheading mt-4"><span>Headlinez är en kontantfri frisörsalong i vasastan, det är av säkerhetsskäl som vi beslutat detta. Prislistan visar priser på de vanligaste behandlingarna, för ett mer exakt pris är du välkommen till oss för en kort konsultation som är kostnadsfri.<br><br></span></p>

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
                          <th class="text-left">Färgning</th>
                          <th class="text-left">Pris</th>
                        </tr>
                      </thead>
                      <tbody>
                        <tr v-for="item in fargningar" :key="item.name">
                          <td><span class="name">{{ item.name }}</span> <span v-if="item.detail" class="detail">{{ item.detail }} </span></td>
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
                          <th class="text-left">Slingor</th>
                          <th class="text-left">Pris</th>
                        </tr>
                      </thead>
                      <tbody>
                        <tr v-for="item in slingor" :key="item.name">
                          <td><span class="name">{{ item.name }}</span> <span v-if="item.detail" class="detail">{{ item.detail }} </span></td>
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
        name: 'Damklippning, tvätt & styling med värmeverktyg',
        price: 450,
      },
      {
        name: 'Tvätt & Fön',
        price: 300,
      },
      {
        name: 'Herrklippning tvätt klipp & styling',
        price: 380,
      },
      {
        name: 'Klippning + skägg med kniv',
        price: 540,
      },
      {
        name: 'Skägg trimning',
        price: 150,
      },
      {
        name: 'Skägg trimning + kniv',
        price: 250,
      },
      {
        name: 'Snaggning',
        price: 180,
      },
      
    ],
    fargningar: [
        {
          name: 'Bottenfärg',
          detail: 'Klippning ingår ej',
          price: 'Från 690',
        },
        {
          name: 'Färgning -  hela håret',
          price: '-',
        },
        {
          name: 'Kort',
          detail: 'Klippning ingår ej',
          price: 'Från 790',
        },
        {
          name: 'Mellan',
          detail: 'Klippning ingår ej',
          price: 'Från 890',
        },
        {
          name: 'Långt',
          detail: 'Klippning ingår ej',
          price: 'Från 1100',
        },
        {
          name: 'Med klippning',
          price: '+300',
        }
      ],
      slingor: [
        {
          name: 'Kort',
          detail: 'Klippning ingår ej',
          price: 'Från 700',
        },
        {
          name: 'Mellan',
          detail: 'Klippning ingår ej',
          price: 'Från 900',
        },
        {
          name: 'Långt',
          detail: 'Klippning ingår ej',
          price: 'Från 1200',
        },
        {
          name: 'Med klippning',
          price: '+300',
        },
        {
          name: 'Extra färgtillägg',
          price: '300 - 400',
        },
        {
          name: 'Avfärgning',
          price: 'Konsultation',
        },
        {
          name: 'Olaplex behandling',
          price: 'Från 699',
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

.name{
  clear: both;
  float: left;
}
.detail{
  clear: both;
  float: left;
  font-size: 10px;
}


@media only screen and (min-width: 768px) {

  
  
  

}
</style>
