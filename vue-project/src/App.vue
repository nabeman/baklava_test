<template>
  <baklava-editor :view-model="baklava"/>
</template>

<script>
import { defineComponent } from 'vue';
import { EditorComponent, useBaklava } from '@baklavajs/renderer-vue';
import '@baklavajs/themes/dist/syrup-dark.css';

// import Node
import MyNode from "./components/MyNode.js"

export default defineComponent({
  components: {
    "baklava-editor": EditorComponent,
  },
  setup(){
    const baklava = useBaklava();
    // register Node
    baklava.editor.registerNodeType(MyNode);
    return { baklava };
  }
})
</script>