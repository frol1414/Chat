<template>
  <v-layout
    column
    justify-center
    align-center
  >
    <v-flex xs12 sm8 md6>
      <v-btn @click="message">New message</v-btn>
    </v-flex>

  </v-layout>
</template>

<script>

export default {
  sockets: {
    connect() {
      console.log("clietn io connect")
    }
  },
  methods: {
    message() {
      this.$socket.emit('createMessage', {
        text: 'FROM client'
      })
    }
  }
}
</script>
