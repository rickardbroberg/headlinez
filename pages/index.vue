<template>
    
    <div class="container container--fluid">
        <div class="layout row wrap">
          
          <div class="flex my-2 text-left xs12">
            <h1>Headlinez din frisör i Vasastan</h1> 
            <p class="feed-subheading mt-4"><span>Färgar, slingar, klipper och tonar ditt hår till perfektion, alltid nöjd kund garanti. följ mig på instagram: @jack.sharoian</span> eller <a href="https://headlinez.bokadirekt.se" target="_blank">boka din nästa tid</a> nu</p></div>

          
          <div class="flex xs12 align-center hidden-md-and-down"><hr role="separator" aria-orientation="horizontal" class="grey feed-border v-divider theme--light"></div>
          
          
        
          <div v-for="(product, p) in products" :key="p" class="flex zx12 sm4 lg3">
            <div class="align-items-center">
              <div class="px-0 v-list-item theme--light" tabindex="-1">
                <div class="v-list-item__content text-left">
                  <div class="v-list-item__title body-1 font-weight-medium" height="18">
                    {{ product.title }}
                  </div>
                </div>
              </div>
            </div>
            <div class="v-card v-card--flat v-sheet v-sheet--tile theme--light transparent">
              
                <div class="v-responsive v-image image-feed">
                  <div class="v-responsive__sizer" style="padding-bottom: 178.571%;"></div>
                  
                  <video v-if="product.video" width="100%" controls :src="product.video"></video>
                  <div v-else class="v-image__image v-image__image--cover" 
                  :style="{ backgroundImage: `url(${product.image})`, backgroundPosition: 'center center' }"></div>

                  <!-- style='background-image: url("product.image"); background-position: center center;' -->
                  <div class="v-responsive__content"></div>
                </div>  
              
            </div>
          </div>
        
        

      </div>
    </div>
    

     
      
  
</template>

<script>
import Vue from 'vue'
import Vuetify from 'vuetify'
import 'vuetify/dist/vuetify.min.css'
// import myVideo from 'vue-video'

Vue.use(Vuetify)

export default {
  head () {
    return {
      title: 'Din frisör i Vasastan, Stockholm',
      meta: [
        { hid: 'description', name: 'description', content: 'Headlinez är en frisör i Vasastan, Stockholm som hyr in sig på salongen Hårfängan.' },
        { hid: 'keywords', name: 'keywords', content: 'frisör, vasastan, stockholm, hårklippning, hairdresser' }
      ]
    }
  },
  data: () => ({
    link: '/kontakt',
    products: [
      {
        icon: 'mdi-email-open',
        title: 'Färginspiration',
        video: 'IMG_8938.mp4'
      },
      {
        icon: 'mdi-email-open',
        title: 'Frisyrinsporation för män',
        image: '/klippning.jpg'
      },
      {
        icon: 'mdi-inbox',
        title: 'Frisyrinsporation för män',
        image: '/klippning-3.jpg'
      },
      {
        icon: 'mdi-inbox',
        title: 'Inspiration för hårfäg',
        video: 'IMG_8939.mp4'
      },
      {
        icon: 'mdi-email-open',
        title: 'Före och efter resultat',
        image: '/before-after-1.jpg'
      },
      {
        icon: 'mdi-star',
        title: 'Färgat blont',
        image: '/blonde.jpg'
      },
      {
        icon: 'mdi-star',
        title: 'Men hairstyle',
        video: 'IMG_8932.mp4'
      },
      {
        icon: 'mdi-email-open',
        title: 'Färg och klippning',
        image: '/before-after-2.jpg'
      },
      {
        icon: 'mdi-inbox',
        title: 'Fade klippning',
        image: '/klippning-4.jpg'
      },
      {
        icon: 'mdi-inbox',
        title: 'Blondering',
        video: 'IMG_8936.mp4'
      },
      {
        icon: 'mdi-star',
        title: 'Före klippning',
        image: '/klipp-after-2.jpg'
      },
      {
        icon: 'mdi-send',
        title: 'Efter fade klippning',
        image: '/klipp-after-1.jpg'
      },
      
      {
        icon: 'mdi-email-open',
        title: 'Inspiration för färgning',
        image: '/fargning-1.jpg'
      },
      {
        icon: 'mdi-email-open',
        title: 'Fadeklippning med bena',
        image: '/klippning-2.jpg'
      },
      {
        icon: 'mdi-send',
        title: 'Fadeklippning med markering',
        image: '/klippning-1.jpg'
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


@media only screen and (max-width: 768px) {
  
  .v-card{
    vertical-align: top;
  }
  .flex{
    float: left;
    clear: both;
    width:100%;
  }
  
  

}
</style>
