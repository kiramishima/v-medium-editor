<template>
  <div class="grid gap-4 grid-cols-6">
    <div class="col-span-1 bg-yellow-400 block static">
      <div class="rounded-full bg-purple-500 h-10 w-10 items-center justify-center float-right my-2" @click="onClick">
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M12 6v6m0 0v6m0-6h6m-6 0H6" />
        </svg>
      </div>

      <div class="rounded-full bg-purple-500 h-7 w-7 items-center justify-center my-3 mx-2 float-right fixed -right-3">
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M12 6v6m0 0v6m0-6h6m-6 0H6" />
        </svg>
      </div>
    </div>
    <div class="editor bg-transparent prose-xl col-span-5 p-2 h-14 w-full border-none text-black" ref="editor">
      <p>My father’s family name being <a href="https://en.wikipedia.org/wiki/Pip_(Great_Expectations)">Pirrip</a></p>
      <img src="https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png" alt="">
    </div>
  </div>
</template>

<style lang="scss">
.editor {
  outline: none;
  margin: 0 0 20px 0;
  padding: 0 0 20px 0;
  border-bottom: 1px solid #dbdbdb;
}
</style>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import MediumEditor from 'medium-editor';

@Options({
    name: 'Editor',
    props: {
      readOnly: Boolean,
      editor: MediumEditor
    }
})
export default class Editor extends Vue {
  readOnly = false;
  editor!: MediumEditor.MediumEditor;
  mounted() {
    console.log("Mounted")
    this.editor = new MediumEditor((this.$refs.editor as HTMLDivElement),
    {
      paste: {cleanPastedHTML: true, forcePlainText: true},
      autoLink: true,
      imageDragging: true
    });
  }

  onClick() {
    console.log("Clicked");
  }
}
</script>