<!-- eslint-disable eqeqeq -->
<!-- eslint-disable eqeqeq -->
<template>
  <q-page padding>
  <input v-model="message"
  @keyup="handlekeyup"
  @keyup.enter="enterMethod"
  >
  // By using V-show it will make display none when condition does not match and vice versa
  <h5 class="border-gray" v-show="message.length>0">{{message}}</h5>
  <button @click="emptyMessage">Vanish input data</button>
  </q-page>
</template>

<script>
export default {
  data () {
    return {
      message: 'We Can Bind Data of input bar and Data property value'
    }
  },
  methods: {
    emptyMessage () {
      this.message = ''
    },
    handlekeyup (e) {
      // eslint-disable-next-line eqeqeq
      if (e.keyCode == 27) {
        alert('You Pressed ESC!!')
      } else {
        console.log(e.keyCode)
      }
    },
    enterMethod () { alert(this.message) }
  }
}
</script>

<style>
.border-gray{
  border: 3px solid gray;
}
</style>
