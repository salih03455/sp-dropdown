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
          value: 1313123,
          title: 'Mercedes &#128512;'
        },
        {
          value: 2424242,
          title: 'Audi &#128513;'
        },
        {
          value: 3445465,
          title: 'Seat &#128514; <b>(My Binek)</b>'
        },
        {
          value: 6756454,
          title: 'Suzuki &#128519;'
        }
      ],
      selectedItem: null,
      config: {
        outside: true
      }
    }
  },
  methods: {
    getSelected(selectedItem) {
      this.selectedItem = selectedItem;
      console.log(this.selectedItem);
    }
  }
});
</script>

<template>
  <div id="app">
    <sp-dropdown
      :title=title
      :list=list
      :config=config
      @onSelected="getSelected"
    />
  </div>
</template>
