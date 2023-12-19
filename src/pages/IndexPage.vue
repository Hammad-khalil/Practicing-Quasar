<template>
  <q-page padding>
  <input v-model="message"/>
  <h5>{{message}}</h5>
  </q-page>
</template>

<script>
export default {
  data () {
    return {
      message: 'We Can Bind Data of input bar and Data property value'
    }
  }
}
</script>

<style>
</style>
