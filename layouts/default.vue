

<template>
  <v-app>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app

    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar
      :clipped-left="clipped"
      fixed
      app
      class="black lighten-1 text-center"
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      
    
      
      <v-toolbar-title v-text="title" />
      <v-spacer />
      
    </v-app-bar>
    
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>

    
    
    <v-card height="100px">
    <v-footer
      v-bind="localAttrs"
      :padless="padless"
    >
      <v-card
        flat
        tile
        width="100%"
        class="black lighten-1 text-center"
      >
        <v-card-text>
          <v-btn
            v-for="(item, i) in items"
            :key="i"
            :to="item.to"
            router
            exact
            class="mx-2"
          >
            <v-icon size="24px">{{ item.icon }}</v-icon>
          </v-btn>
        </v-card-text>

        <v-divider></v-divider>

        <v-card-text class="white--text">
          {{ new Date().getFullYear() }} — Headlinez
        </v-card-text>
      </v-card>
    </v-footer>

    
  </v-card>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-home',
          title: 'Start',
          to: '/',
          default: 'default',
          absolut: 'absolute',
          fixed: 'fixed'
        },
        {
          icon: 'mdi-square-inc-cash',
          title: 'Prislista',
          to: '/priser'
        }
        ,
        {
          icon: 'mdi-calendar',
          title: 'Kontakt & Bokning',
          to: '/kontakt'
        }
      ],
      padless: true,
      variant: 'absolute',
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Headlinez - din frisör i Vasastan'
    }
  },
  computed: {
    localAttrs () {
      const attrs = {}

      if (this.variant === 'default') {
        attrs.absolute = false
        attrs.fixed = false
      } else {
        attrs[this.variant] = true
      }
      return attrs
    },
  },
  head (){
    return {
      title: 'Headlinez en frisörsalong i vasasataden',
      meta: [
        { hid: 'description', name: 'description', content: 'Headlinez din frisör i vasastan, stockholm' },
        { hid: 'keywords', name: 'keywords', content: 'frisör, vasastaden, stockholm, hårklippning' }
      ]
    }
  }
}
</script>
<style>
  
  body,p{
    color:#000;
    font-family: 'Source Sans Pro', sans-serif;
  }
  header{
    color:#fff !important;
  }
  button{
    color:#fff !important;
  }
  a{
    color:#000;
    font-weight:700; 
  }
  h1,h2,h3{
    font-family: 'Source Sans Pro', sans-serif;
    font-weight: 700;
    color:#000;
    width: 100%;
    /* font-family: 'Kaushan Script', cursive; */
  }
  h1{
    font-size: 40px;
    font-weight: 400;
  }
  h2{
    font-size: 38px;
    margin-bottom: 5%; 
    float: none; 
    display: inline-block;  
    padding: 0em; 
    line-height: 100%; 
    min-height: 32px;
  }

  .v-content__wrap{
    background-color: #fff;
  }
  footer a{
    background-color: #000;
  }

  @media only screen and (min-width: 768px) {

  
    h1,h2,h3,.date{
      font-family: 'Source Sans Pro', sans-serif;
      /* font-family: 'Kaushan Script', cursive; */
    }
    h1{
      font-size: 40px;
    }
    h2{
      font-size: 36px;
      margin-bottom: 5%; 
      float: none; 
      display: inline-block;  
      padding: 0em; 
      line-height: 100%; 
      min-height: 32px;
    }
    

  }
</style>
