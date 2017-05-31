<template>
  <div id="app">
    <container>
      <img src="./assets/logo.png">
      <cerebral></cerebral>
      <foo></foo>
    </container>
  </div>
</template>

<script>
// import Hello from './components/Hello';

import Vue from 'vue/dist/vue'
import {Controller} from 'cerebral'
import {Container, connect} from 'cerebral/vue'
import Cerebral from './components/Cerebral'
import Foo from './components/Foo'


const controller = Controller({
  state: {
    foo: 'Superduper!',
    mylist: [{ obst: 'Äpfel' }, { obst: 'Birnen' }, { obst: 'Tomaten' }]
  }
})

export default {
  name: 'app',
  components: {
    container: Container(controller),
    Cerebral,
    Foo
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
