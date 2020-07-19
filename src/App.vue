<template>
  <PageComponent v-if="config.about" v-bind:config="config"/>
</template>

<script lang="ts">

import PageComponent from './components/PageComponent.vue'
import firebase from 'firebase'
import devConfig from './../public/config/config.json'

async function getConfig () {
  const firebaseConfig = {
    apiKey: 'AIzaSyAuC_tdIDdOmOsw2Rq1lDW4R_lNdQDiQUU',
    authDomain: 'williamperacchio.firebaseapp.com',
    databaseURL: 'https://williamperacchio.firebaseio.com',
    projectId: 'williamperacchio',
    storageBucket: 'williamperacchio.appspot.com',
    messagingSenderId: '138581375338',
    appId: '1:138581375338:web:fa3ec0b59ae2189af6cd13',
    measurementId: 'G-0K8KRK0SJ4'
  }

  // Initialize Firebase
  firebase.initializeApp(firebaseConfig)
  let response = await firebase.database().ref('/').once('value')
  return response
}

export default {
  components: {
    PageComponent
  },
  data () {
    return {
      config: devConfig || this.setConf()
    }
  },
  methods: {
    async setConf () {
      await getConfig().then((snapshot) => {
        this.config = snapshot.val()
      })
    }
  }
}
</script>

