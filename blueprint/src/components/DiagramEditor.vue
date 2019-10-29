<template>
  <div id="diagram-editor" v-html="schema">
  </div>
</template>

<script>
  export default {
    name: 'DiagramEditor',
    props: ['schema'],
    data() {
      return {
      }
    }
  }
</script>

<style></style>