<script>
import Vue from 'vue';
import VueElasticTextarea from '@/vue-elastic-textarea.vue';

export default Vue.extend({
  name: 'ServeDev',
  components: {
    VueElasticTextarea
  }
});
</script>

<template>
  <div id="app">
    <vue-elastic-textarea />
  </div>
</template>
