<template>
  <div>
    <section>
      <nav 
        ref="navbar"
        class="navbar is-spaced"
        role="navigation" 
        aria-label="main navigation">
        <div class="container">
          <div 
            class="navbar-brand" 
          >
            <a
              class="navbar-item" 
              href="/">
              <wifi-logo />
            </a>            
            <div class="navbar-burger">
              <span/>
              <span/>
              <span/>
            </div>
          </div>
         
          <div class="navbar-end">                        
            <a 
              href="" 
              class="button is-rounded is-outlined mrs">front-end</a>
            <a 
              href="" 
              class="button is-rounded is-outlined mrs">back-end</a>
            <a 
              href="" 
              class="button is-rounded is-outlined mrs">all-end</a>           
          </div>
       
        </div>
      </nav>
    </section>
    <section class="main-content columns">
      <div class="container column is-12">
        <nuxt />
      </div>
    </section>
  </div>
</template>

<script>
import wifiLogo from '@/components/WifiLogo'

export default {
  components: { wifiLogo },
  data() {
    return {
      timeline: null
    }
  },
  mounted() {},
  methods: {}
}
</script>
<style>
html {
  height: 100%;
}
/** body {
 height: 100%;
  background: #4ca3fb;
  background: -moz-linear-gradient(-45deg, #4ca3fb 1%, #deecf9 100%);
  background: -webkit-linear-gradient(-45deg, #4ca3fb 1%, #deecf9 100%);
  background: linear-gradient(135deg, #4ca3fb 1%, #deecf9 100%);
  filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#4ca3fb', endColorstr='#deecf9',GradientType=1 );
}
.navbar {
  background: #4ca3fb;
  background: -moz-linear-gradient(-45deg, #deecf9 1%, #4ca3fb 100%);
  background: -webkit-linear-gradient(-45deg, #deecf9 1%, #4ca3fb 100%);
  background: linear-gradient(135deg, #deecf9 1%, #4ca3fb 100%);
  filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#deecf9', endColorstr='#4ca3fb',GradientType=1 );
} **/
.navbar-link {
  color: #6d6f71 !important;
}
</style>
