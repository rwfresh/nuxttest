<template>
  <section class="section">
    <div class="columns ">
      <div 
        v-for="(feature, i) of features"
        :key="i"
        class="column">
        <div class="card has-background-grey-lighter">
          <header class="card-header">
            <p class="card-header-title has-text-grey">
              {{ feature.title }}
            </p>
          </header>
          <div class="card-content">
            <div class="content has-text-centered">
              <b-icon 
                :icon="feature.icon"
                size="is-large"
                type="is-primary" />
            </div>
          </div>
          <footer class="card-footer">
            <div 
              class="card-footer-item"
              v-html="feature.content" />
          </footer>
        </div>
      </div>
    </div>
    <div class="columns">
      <div 
        class="card has-background-info" 
        style="width:100%; height:500px">
        <div class="card-content">
          <div class="content has-text-centered">
            <h1>Box 1</h1>
            <svg 
              version="1.1" 
              xmlns="http://www.w3.org/2000/svg" 
              xmlns:xlink="http://www.w3.org/1999/xlink" 
              x="0px" 
              y="0px"
              viewBox="0 0 100 100" 
              style="border:1px solid #000000" 
              xml:space="preserve">
              <g 
                fill="transparent" 
                stroke="green" 
                stroke-width=".5" 
                transform="translate(50,40)"/>
            </svg>
          </div>
        </div>
      </div>
      <div 
        class="card has-background-grey-lighter" 
        style="width:100%; height:500px">
        <div class="card-content">
          <div class="content has-text-centered">
            <h1>Box 1</h1>
          </div>
        </div>
      </div>
    </div>
    <div class="columns">
      <div 
        class="card has-background-info" 
        style="width:100%; height:500px">
        <div class="card-content">
          <div class="content has-text-centered">
            <h1>Box 1</h1>
          </div>
        </div>
      </div>
      <div 
        class="card has-background-grey-lighter" 
        style="width:100%; height:500px">
        <div class="card-content">
          <div class="content has-text-centered">
            <h1>Box 1</h1>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import SvgCircle from '@/components/SvgCircle'

export default {
  name: 'HomePage',
  components: { SvgCircle },
  data() {
    return {
      features: [
        {
          icon: 'github-circle',
          title: 'Free',
          content: `<span>Open source on <a href="https://github.com/buefy/buefy"> GitHub</a></span>`
        },
        {
          icon: 'cellphone-link',
          title: 'Responsive',
          content: `<span><b class="has-text-grey">Every</b> component is responsive</span>`
        },
        {
          icon: 'alert-decagram',
          title: 'Modern',
          content: `<span>Built with <a href="https://vuejs.org/">Vue.js</a> and <a href="http://bulma.io/">Bulma</a></span>`
        },
        {
          icon: 'arrange-bring-to-front',
          title: 'Lightweight',
          content: `<span>No other internal dependency</span>`
        }
      ],
      circles: [],
      circle: '<circle cx="40" cy="40" r="25" />'
    }
  }
}
</script>
