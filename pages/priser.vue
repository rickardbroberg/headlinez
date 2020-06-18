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

                  <v-simple-table class="theme--light">
                    <template v-slot:default>
                      <thead>
                        <tr>
                          <th class="text-left">Balayage + klippning</th>
                          <th class="text-left">Pris</th>
                        </tr>
                      </thead>
                      <tbody>
                        <tr v-for="item in balayage" :key="item.name">
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
  head () {
    return {
      title: 'Priser',
      meta: [
        { hid: 'description', name: 'description', content: 'Headlinez prislista för de vanligaste behandlingarna.' },
        { hid: 'keywords', name: 'keywords', content: 'prislista, färgning, slingor, klippning, hårklippning, tvätt och fön' }
      ]
    }
  },
  data: () => ({
    
    klippningar: [
      {
        name: 'Damklippning, tvätt & styling med värmeverktyg (60min)',
        price: 520,
      },
      {
        name: 'Damklippning (student), tvätt & styling med värmeverktyg (60min)',
        price: 420,
      },
      {
        name: 'Tvätt & Fön (45min)',
        price: 400,
      },
      {
        name: 'Herrklippning tvätt klipp & styling (30/45min)',
        price: 420,
      },
      {
        name: 'Klippning + skägg med kniv (60min)',
        price: 650,
      },
      {
        name: 'Herrklippning (student) tvätt klipp & styling (30min)',
        price: 380,
      },
      {
        name: 'Skägg med kniv (30min)',
        price: 300,
      },
      {
        name: 'Barnklippning',
        price: 350,
      },
      
    ],
    fargningar: [
        {
          name: 'Bottenfärg',
          detail: 'Klippning ingår ej, pris varierar',
          price: 'Från 800',
        },
        {
          name: 'Bottenfärg + klippning',
          detail: 'Pris varierar',
          price: 'Från 1400',
        },
        {
          name: 'Blekning utväxt + nyansering',
          detail: 'Klippning ingår ej, pris varierar',
          price: 'Från 1600',
        },
        {
          name: 'Färgning -  hela håret',
          price: '-',
        },
        {
          name: 'Kort',
          detail: 'Klippning ingår ej, pris varierar',
          price: 'Från 1000',
        },
        {
          name: 'Mellan',
          detail: 'Klippning ingår ej, pris varierar',
          price: 'Från 1600',
        },
        {
          name: 'Långt',
          detail: 'Klippning ingår ej, pris varierar',
          price: 'Från 2000',
        },
        {
          name: 'Med klippning',
          price: '+400',
        }
      ],
      slingor: [
        {
          name: 'Slingor + nyansering, klippning ingår ej',
          price: '-',
        },
        {
          name: 'Kort',
          detail: 'Pris varierar',
          price: 'Från 1800',
        },
        {
          name: 'Mellan',
          detail: 'Pris varierar',
          price: 'Från 2200',
        },
        {
          name: 'Långt',
          detail: 'Pris varierar',
          price: 'Från 3000',
        },
        {
          name: 'Slingor + nyansering + klippning',
          price: '-',
        },
        {
          name: 'Kort',
          detail: 'Pris varierar',
          price: 'Från 2200',
        },
        {
          name: 'Mellan',
          detail: 'Pris varierar',
          price: 'Från 3000',
        },
        {
          name: 'Långt',
          detail: 'Pris varierar',
          price: 'Från 3800',
        }
      ],
      balayage: [
        {
          name: 'Kort',
          detail: 'Pris varierar',
          price: 'Från 2500',
        },
        {
          name: 'Mellan',
          detail: 'Pris varierar',
          price: 'Från 3200',
        },
        {
          name: 'Långt',
          detail: 'Pris varierar',
          price: 'Från 3800',
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
