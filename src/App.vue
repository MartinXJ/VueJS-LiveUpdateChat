<template>
  <div id="app">
    <Login />
    <b-container>
      <NavBar :logged_user="logged_user_username" />
      <b-row class="main-area">
        <b-col cols="4" class="users">
          <Users />
        </b-col>
        <b-col cols="8" class="messages-area">
          <div class="messages-main">
            <div v-if="!current_chat_channel" class="select-chat text-center">
              Select a user to start chatting... 
            </div>
            <Messages 
              v-else 
              :active_chat="active_chat_id" 
              :messages="messages[current_chat_channel]"
            /> 
          </div>
          <MessageInput />
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
