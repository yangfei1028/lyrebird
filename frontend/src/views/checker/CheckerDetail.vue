<template>
  <div v-if="checkerDetail">
    <code-editor :language="codeType" :content="checkerDetail" class="checker-detail"></code-editor>
  </div>
  <div v-else class="checker-empty">
    No selected script
  </div>
</template>

<script>
import CodeEditor from '@/components/CodeEditor.vue'

  export default {
    components:{
      CodeEditor
    },
    data () {
      return {
        codeType: 'python'
      }
    },
    computed: {
      checkerDetail() {
        return this.$store.state.checker.focusCheckerDetail
      }
    }
  }
</script>

<style scoped>
  .checker-detail {
    height: calc(100vh - 71px);
    /* total:100vh
    header: 38px
    padding: 5px
    table
    padding: 5px
    padding: 5px
    footer: 28px
    */
  }
</style>
