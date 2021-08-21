<template>
  <div class="container">
    <sp-dropdown
      :title=title
      :list=list
      @onSelected="getSelected"
    />
    <div>asdasdasdasd asdasdd asdasdasd asdsad</div>
  </div>
</template>

<script>
import SpDropdown from './components/SpDropdown.vue'

export default {
  name: 'App',
  data() {
    return {
      title: 'Choose Auto',
      list: [
        {
          value: 1313123,
          title: '<b>Mercedes</b>'
        },
        {
          value: 2424242,
          title: 'Audi'
        },
        {
          value: 3445465,
          title: 'Seat'
        },
        {
          value: 6756454,
          title: 'Suzuki'
        }
      ],
      selectedItem: null
    }
  },
  components: {
    SpDropdown
  },
  methods: {
    getSelected(selectedItem) {
      this.selectedItem = selectedItem;
      console.log(this.selectedItem);
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
.container {
    width: 768px;
    margin: auto;
    padding: 30px;
    border-radius: 15px;
    box-shadow: 1px 1px 5px #ddd;
    min-height: 400px;
}
</style>
