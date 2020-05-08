<template>
  <textarea
    class="elastic__textarea"
    v-model="currentValue"
    @input="resize"
    @focus="resize"
    ref="textarea"
  ></textarea>
</template>

<script>
export default {
  name: 'VueElasticTextarea',
  data() {
    return {
      currentValue: this.value ? this.value.replace(/(<([^>]+)>)/ig,"") : '',
    };
  },
  props: {
    /**
     * Initial value
     * @default ''
     * @type { String, Number }
     */
    value: {
      type: [String, Number],
      default: '',
    },
  },
  methods: {
    resize() {
      const textarea = this.$refs.textarea;
      textarea.style.height = 'auto';
      textarea.style.height = textarea.scrollHeight + textarea.offsetHeight - textarea.clientHeight + "px";
      this.$emit('input', this.currentValue);
    },
  },
  mounted() {
    this.$nextTick(() => {
      this.resize();
    });
  },
};
</script>

<style scoped>
  .elastic__textarea {
    resize: none;
    box-sizing: border-box;
    overflow: hidden;
    min-height: 60px;
  }
</style>
