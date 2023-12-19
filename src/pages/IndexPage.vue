<template>
  <q-page padding>
  <input v-model="message"/>
  <h5>{{message}}</h5>
  <button @click="message=' '">Vanish input data</button>
  </q-page>
</template>

<script>
export default {
  data () {
    return {
      message: 'We Can Bind Data of input bar and Data property value'
    }
  // },
  // methods: {
  //   emptyMessage () {
  //     this.message = ''
  //   }
  // }
  }
}
</script>

<style>
</style>
