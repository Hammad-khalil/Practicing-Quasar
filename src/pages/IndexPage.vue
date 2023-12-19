<!-- eslint-disable eqeqeq -->
<!-- eslint-disable eqeqeq -->
<template>
  <q-page padding>

  <button @click="count++">{{count}}</button>
  <input v-model="message"
  @keyup="handlekeyup"
  @keyup.enter="enterMethod"
  >
   <!-- By using V-show it will make display none when condition does not match and vice versa -->
  <h5
   v-if="message.length>0" class="border-gray"
  >{{message}}</h5>
  <h6 v-else> No Message Left 😐</h6>
  <button @click="emptyMessage">Vanish input data</button>
  <hr>

  <h6>{{messageUppercase}}</h6>
  </q-page>
</template>

<script>
export default {
  data () {
    return {
      message: 'Enter any text',
      count: 0
      // message: 'We Can Bind Data of input bar and Data property value'
    }
  },
  computed: {
    messageUppercase () {
      console.log('Message Uppercase Button was fired !!!')
      return this.message.toUpperCase()
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
