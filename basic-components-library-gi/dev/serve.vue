<script>
import Vue from 'vue';
// Uncomment import and local "components" registration if library is not registered globally.
// import { BasicComponentsLibraryGiSample } from '@/entry.esm';

export default Vue.extend({
  name: 'ServeDev',
  // components: {
  //  BasicComponentsLibraryGiSample,
  // }
});
</script>

<template>
  <div id="app">
    <basic-components-library-gi-sample />
  </div>
</template>
