<template>
  <section>
    <div>
      <sample-component :title="indexTitle">
        <div class="come">
          slot example aaaaaa
        </div>
        <div slot="named">
          Tetsuya slot!!!
        </div>
      </sample-component>
      <nuxt-link to="/about">ABOUT</nuxt-link> 
    </div>
  </section>
</template>

<script>
import SampleComponent from '~/components/SampleComponent.vue'

export default {
  components: {
    SampleComponent
  },
   data() {
    return {
      indexTitle: 'Nuxt.js Handson!'
    }
  }
}
</script>

<style>
  
</style>
