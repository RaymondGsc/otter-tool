<script setup lang="ts">
import 'cherry-markdown/dist/cherry-markdown.css';
import Cherry from 'cherry-markdown';
import { onMounted } from 'vue';

onMounted(() => {
  new Cherry({
    id: 'markdown-container',
    value: '# welcome to cherry editor!',
    toolbars: {
      theme: 'dark', // light or dark
      showToolbar: true, // false：不展示顶部工具栏； true：展示工具栏; toolbars.showToolbar=false 与 toolbars.toolbar=false 等效
      toolbar: [
        'bold',
        'italic',
        'strikethrough',
        '|',
        'color',
        'header',
        'ruby',
        '|',
        'list',
        'panel',
        'detail',
        {
          insert: [
            'image',
            'link',
            'hr',
            'br',
            'code',
            'formula',
            'table',
            'line-table',
            'bar-table',
            'pdf',
            'word',
          ],
        },
        'graph',
        'settings',
        'export',
      ],
      toolbarRight: [],
      sidebar: [],
    },
  });
});

</script>

<template>
  <div class="md-wrapper">
    <div id="markdown-container"></div>
  </div>
</template>

<style scoped>
.md-wrapper {
  width: 90vw;
  height: calc(100vh - 80px);
}
</style>
