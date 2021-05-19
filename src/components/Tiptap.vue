<template>
  <editor-content :editor="editor" v-if="editor" />
</template>

<script lang="ts">
import { Editor, EditorContent } from '@tiptap/vue-3'
import StarterKit from '@tiptap/starter-kit'
import { defineComponent } from '@vue/runtime-core'

export default defineComponent({
  components: {
    EditorContent,
  },

  data() {
    return {
      editor: null,
    } as { editor: Editor | null }
  },

  mounted() {
    this.editor = new Editor({
      content: '<p>I’m running tiptap with Vue.js. 🎉</p>',
      extensions: [
        StarterKit,
      ],
    })
  },

  beforeUnmount() {
    this.editor?.destroy()
  },
});
</script>