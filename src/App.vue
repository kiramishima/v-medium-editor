<template>
  <main class="w-screen h-screen flex flex-col">
    <medium-editor></medium-editor>
  </main>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import Editor from '@/components/Editor.vue';

@Options({
    name: 'App',
    components: {
      'medium-editor': Editor
    }
})
export default class App extends Vue {
}
</script>
