

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

    <v-navigation-drawer
      v-model="rightDrawer"
      :right="right"
      temporary
      fixed
    >
      <v-list>
        <v-list-item @click.native="right = !right">
          <v-list-item-action>
            <v-icon light>
              mdi-repeat
            </v-icon>
          </v-list-item-action>
          <v-list-item-title>Switch drawer (click me)</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    
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
            v-for="icon in icons"
            :key="icon"
            class="mx-4"
            icon
          >
            <v-icon size="24px">{{ icon }}</v-icon>
          </v-btn>
        </v-card-text>

        <v-divider></v-divider>

        <v-card-text class="white--text">
          {{ new Date().getFullYear() }} — <strong>Headlinez</strong>
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
      icons: [
        'mdi-home',
        'mdi-email',
        'mdi-calendar',
      ],
      items: [
        {
          icon: 'mdi-apps',
          title: 'Start',
          to: '/',
          default: 'default',
          absolut: 'absolute',
          fixed: 'fixed'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Priser',
          to: '/priser'
        }
        ,
        {
          icon: 'mdi-chart-bubble',
          title: 'Kontakt',
          to: '/kontakt'
        }
      ],
      padless: true,
      variant: 'absolute',
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Headlinez - frisörsalong i vasastaden'
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
        { hid: 'description', name: 'description', content: 'Headlinez din frisör i vasastaden' },
        { hid: 'keywords', name: 'keywords', content: 'frisör, vasastaden, stockholm, hårklippning' }
      ]
    }
  }
}
</script>
<style>
  body,p{
    color:#000;
  }
  a{
    color:#000;
    font-weight:700; 
  }
  h1,h2,h3{
    font-family: 'bradley-hand';
    color:#000;
    /* font-family: 'Kaushan Script', cursive; */
  }
  h1{
    font-size: 40px;
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

  @media only screen and (min-width: 768px) {

  
    h1,h2,h3,.date{
      font-family: 'bradley-hand';
      /* font-family: 'Kaushan Script', cursive; */
    }
    h1{
      font-size: 52px;
    }
    h2{
      font-size: 42px;
      margin-bottom: 5%; 
      float: none; 
      display: inline-block;  
      padding: 0em; 
      line-height: 100%; 
      min-height: 32px;
    }
    

  }
</style>
