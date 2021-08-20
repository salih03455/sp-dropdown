<script>
import { defineComponent } from 'vue';
import SpDropdown from '@/sp-dropdown.vue';

export default defineComponent({
  name: 'ServeDev',
  components: {
    SpDropdown
  },
  data() {
    return {
      title: 'dinleyin beni develer',
      list: [
        {
          title: 'Salih',
          value: 123434
        },
        {
          title: 'Maho',
          value: 343556
        },
        {
          title: 'Hamza',
          value: 345890
        },
        {
          title: 'Cevdet',
          value: 876543
        }
      ]
    }
  }
});
</script>

<template>
  <div id="app">
    <sp-dropdown :title=title :list=list />
  </div>
</template>
