<!-- eslint-disable eqeqeq -->
<!-- eslint-disable eqeqeq -->
<template>

 <q-knob
      v-model="value"
      size="45px"
      :thickness="1"
      color="grey-8"
      track-color="light-blue"
      class="q-ma-md"
    />
  <q-page padding>
  <button class="btn" @click="count++">{{count}}</button>
  <input v-model="message"
  @keyup="handlekeyup"
  @keyup.enter="enterMethod"
  :class="{ 'error' : message.length>22}"
  ref="messageInput"
  >
  <div class="totalchar">{{message.length}}  (Total Characters must be under 22)</div>
   <!-- By using V-show it will make display none when condition does not match and vice versa -->
  <h5
   v-if="message.length>0" class="border-gray"
  >{{message}}</h5>
  <h6 v-else> No Message Left 😐</h6>
  <button @click="emptyMessage">Vanish input data</button>
  <hr>

  <h6>{{messageUppercase}}</h6>

  <div class="q-pa-md">
    <q-parallax>
      <template v-slot:media>
        <img src="https://cdn.quasar.dev/img/parallax2.jpg">
      </template>

      <template v-slot:content="scope">
        <div
          class="absolute column items-center"
          :style="{
            opacity: 0.45 + (1 - scope.percentScrolled) * 0.55,
            top: (scope.percentScrolled * 60) + '%',
            left: 0,
            right: 0
          }"
        >
          <img src="https://cdn.quasar.dev/logo-v2/svg/logo-mono-white.svg" style="width: 150px; height: 150px">
          <div class="text-h3 text-white text-center">Quasar Framework</div>
          <div class="text-h6 text-grey-3 text-center">
            v{{ $q.version }}
          </div>
        </div>
      </template>
    </q-parallax>
  </div>

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
  },
  //   👇 These Are LifeCycle Hooks 👇
  mounted () {
    this.$refs.messageInput.className = 'bg-green'
  }

}
</script>

<style>
button input {
  font-size: 23px;
}
.border-gray{
  border: 3px solid gray;
}
.btn{
  position: absolute;
  top: 0%;
  left: 18%;
}
.error{
  color: red;
  background-color: pink;
}

.totalchar{
  position: absolute;
  left: 18%;
  color: white;
  background-color: firebrick;
}
</style>
