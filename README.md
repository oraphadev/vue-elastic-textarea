## Features & characteristics:
* No dependencies
* Very lean and simple

## Example
![](demo/vue-elastic-textarea.gif)

## Install & basic usage

```bash
npm install vue-elastic-textarea
``` 

```vue
<template>
  <vue-elastic-textarea v-model="value" />
</template>

<script>
import VueElasticTextarea from 'vue-elastic-textarea';
export default {
  data() {
    return {
      value: "Hello, world",
    };
  },
  components: { VueElasticTextarea },
}
</script>
```