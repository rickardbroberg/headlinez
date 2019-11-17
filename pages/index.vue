<template>
    
    <div class="container container--fluid">
        <div class="layout row wrap">
          
          <div class="flex my-5 text-left xs12">
            <h1>Headlinez din frisör i vasastan</h1> 
            <p class="feed-subheading mt-4"><span>Färgar, slingar, klipper och tonar ditt hår till perfektion, alltid nöjd kund garanti.</span></p></div>

          
          <div class="flex xs12 align-center hidden-md-and-down"><hr role="separator" aria-orientation="horizontal" class="grey feed-border v-divider theme--light mt-5"></div>

        
          <div v-for="(product, p) in products" :key="p" class="flex zx12 sm4 lg3">
            <div class="align-items-center">
              <div class="px-0 v-list-item theme--light" tabindex="-1">
                <div class="v-list-item__content text-left">
                  <div class="v-list-item__title body-1 font-weight-medium" height="18">
                    {{ product.title }}
                  </div>
                  <div class="v-list-item__subtitle caption">
                    {{ product.text }}
                  </div>
                </div>
              </div>
            </div>
            <div class="v-card v-card--flat v-sheet v-sheet--tile theme--light transparent">
              <a href="">
                <div class="v-responsive v-image grey lighten-2 image-feed">
                  <div class="v-responsive__sizer" style="padding-bottom: 178.571%;"></div>
                  <div class="v-image__image v-image__image--cover" 
                  :style="{ backgroundImage: `url(${product.image})`, backgroundPosition: 'center center' }"></div>

                  <!-- style='background-image: url("product.image"); background-position: center center;' -->
                  <div class="v-responsive__content"></div>
                </div>  
              </a>
            </div>
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
    products: [
      {
        icon: 'mdi-inbox',
        title: 'Färgning',
        text: 'Blakning eller färgning',
        image: '/fargning.jpg'
      },
      {
        icon: 'mdi-star',
        title: 'Slingor',
        text: 'Ljusa eller mörka, ombre',
        image: '/blonde.jpg'
      },
      {
        icon: 'mdi-send',
        title: 'Toning',
        text: 'Nyanser med liv',
        image: '/blonde.jpg'
      },
      {
        icon: 'mdi-email-open',
        title: 'Klippning',
        text: 'Herr och damklippning',
        image: '/klippning.jpg'
      },
    ],
    
  }),
  components: {
    
  }
}
</script>

<style>
  


.image-feed {
    border-radius: 20px !important;
}

.layout .flex {
    padding: 12px;
}


@media only screen and (min-width: 768px) {

  
  
  

}
</style>
