<script lang="ts">
import palaceTextEdit from '@/lib-components/palace-text-edit.vue';
import Vue from 'vue';
// Uncomment import and local "components" registration if library is not registered globally.
// import { PalaceVcomponentsSample } from '@/entry.esm';

export default Vue.extend({
  components: { palaceTextEdit },
  name: 'ServeDev',
  // components: {
  //  PalaceVcomponentsSample,
  // }
});
</script>

<template>
  <div id="app">
    <palace-vcomponents-sample />

  </div>
</template>
