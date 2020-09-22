<template>
  <div class="home container">
    <section class="control">
      <div class="buttons">
        <b-button type="is-info is-light" @click="fetch('nz')">GET NZ</b-button>
        <b-button type="is-info is-light" @click="fetch('au')">GET AU</b-button>
        <b-button type="is-info is-light" @click="fetch('uk')">GET UK</b-button>
      </div>
      <div class="is-divider" data-content="d"></div>
    </section>
    <section class="form" v-if="formData">
      <div class="columns">
        <div class="column">
          <component :is="activeForm" v-bind:formData="formData"></component>
        </div>
        <div class="column">
          <pre>{{formData}}</pre>
        </div>
      </div>
    </section>
    <section class="post">
      <div class="columns">
        <div class="column"><b-button type="is-success ">POST</b-button></div>
        <div class="column"><pre></pre></div>
      </div>
    </section>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
// import axios from 'axios'
import FormNz from '@/components/FormNz.vue'
import FormAu from '@/components/FormAu.vue'
import FormUk from '@/components/FormUk.vue'
import getNz from '../../static/getnz.json'
import getAu from '../../static/getau.json'
import getUk from '../../static/getuk.json'

export default {
  name: 'home',
  data () {
    return {
      countryData: {
        "nz": getNz,
        "au": getAu,
        "uk": getUk
      },
      formData: null,
      activeForm: null
    }
  },
  methods: {
    fetch: function(country) {
      this.formData = this.countryData[country]
      this.activeForm = 'form-' + country
    },
    renderForm () {

    }
  },
  computed: {

  },
  components: {
    FormNz,
    FormAu,
    FormUk
  }
}
</script>
