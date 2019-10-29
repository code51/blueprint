<template>
  <div id="app">
    <div class="columns" style="height: 100vh;">
      <input v-model="schema" />
      <TextEditor :editorValue="schema" @codeChange="codeChange" class="column is-one-quarter"></TextEditor>
      <DiagramEditor :schema="schema" class="column"></DiagramEditor>
    </div>
  </div>
</template>

<script>
import Vue from 'vue'
import Buefy from 'buefy/dist/buefy.css'
import TextEditor from './components/TextEditor.vue'
import DiagramEditor from './components/DiagramEditor.vue'

Vue.use(Buefy);

export default {
  name: 'app',
  data() {
    return {
      schema: 'hehe'
    }
  },
  methods: {
    codeChange(val) {
      this.schema = val;
    }
  },
  components: {
    TextEditor, DiagramEditor
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
