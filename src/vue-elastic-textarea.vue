<template>
  <textarea
    class="elastic__textarea"
    v-model="currentValue"
    @input="resize"
    ref="textarea"
  ></textarea>
</template>

<script>
export default {
  name: 'VueElasticTextarea',
  data() {
    return {
      currentValue: this.value,
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
    resize(event) {
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
    min-height: 30px;
  }
</style>
