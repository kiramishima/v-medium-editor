<template>
    <div class="medium-editor-container" v-if="!readOnly">
        <div class="editor" ref="editor">

        </div>
    </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import MediumEditor from 'medium-editor';

@Options({
    name: 'Editor',
    props: {
        editor: MediumEditor
    }
})
export default class Editor extends Vue {
  editor!: MediumEditor.MediumEditor;
  mounted() {
    console.log("Mounted")
    this.editor = new MediumEditor((this.$refs.editor as HTMLDivElement));
  }
}
</script>