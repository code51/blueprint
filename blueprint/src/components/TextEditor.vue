<template>
  <div id="text-editor">
    <brace style="height: 100%"
           :fontsize="'12px'"
           :theme="'monokai'"
           :mode="'sql'"
           :codefolding="'markbegin'"
           :softwrap="'free'"
           :selectionstyle="'text'"
           :highlightline="true"
           v-html="value"
           @code-change="codeChange"
    >
    </brace>
  </div>
</template>

<script>
  import Brace from 'vue-bulma-brace'
  import 'brace/worker/html'

  export default {
    name: 'TextEditor',
    props: ['editorValue'],
    data() {
      return {
        value: '',
        editor: null
      }
    },
    directives: {
      model: {
        componentUpdated() {
          console.log(123);
        }
      }
    },
    created() {
      this.value = this.editorValue;
    },
    methods: {
      codeChange(val) {
        this.$emit('codeChange', val);
      },
      getContent() {
        console.log(this.editor);
      }
    },
    components: {Brace}
  }
</script>

<style></style>