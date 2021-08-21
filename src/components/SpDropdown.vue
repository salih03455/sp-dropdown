<template>
  <div :class="['sp-dropdown', { active: status }]">
    <div class="sp-dropdown-title" @click="changeStatus()">
      {{ selected ? selected.title : title }} <i />
    </div>
    <div class="sp-dropdown-content">
      <ul>
        <li
          v-for="item in list"
          :key="item.value"
          :data-id="item.value"
          @click="changeSelected(item)">
          {{ item.title }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SpDropdown',
  data() {
    return {
      status: false,
      selected: null
    }
  },
  props: {
    title: String,
    list: Array
  },
  methods: {
    changeStatus() {
      this.status = !this.status;
    },
    changeSelected(item) {
      this.$emit('onSelected', item);
      this.selected = item;
      this.changeStatus();
    }
  }
}
</script>

<style>
  .sp-dropdown {
    display: flex;
    flex-direction: column;
    width: -webkit-fit-content;
    width: -moz-fit-content;
    width: fit-content;
    position: relative;
  }
  .sp-dropdown * {
    box-sizing: border-box;
  }
  .sp-dropdown-title {
    font-size: 20px;
    cursor: pointer;
    border: 1px solid #ddd;
    padding: 8px 14px;
    border-radius: 3px;
  }
  .sp-dropdown-title i {
    display:inline-block;
    border-top: 7px solid;
    border-bottom: 10px solid;
    border-left: 5px solid;
    border-right: 5px solid; 
    border-color: transparent;
    border-top-color: inherit;
    vertical-align: bottom;
    margin-left: 5px;
  }
  .sp-dropdown.active .sp-dropdown-title {
    box-shadow: 0 1px 4px rgb(0 0 0 / 9%);
  }
  .sp-dropdown.active .sp-dropdown-title i {
    border-top: 10px solid;
    border-bottom: 7px solid;
    border-color: transparent;
    border-bottom-color: inherit;
    border-top-color: transparent;
    vertical-align: top;
  }
  .sp-dropdown-content {
    display: none;
    position: absolute;
    top: calc(100% + 5px);
    left: 0;
    border: 1px solid #ddd;
    background: #fff;
    padding: 8px 14px;
    min-width: 100%;
    border-radius: 3px;
    box-shadow: 0 1px 4px rgb(0 0 0 / 9%);
  }
  .sp-dropdown.active .sp-dropdown-content {
    display: block;
  }
  .sp-dropdown-content ul {
    padding: 0;
    margin: 0;
    list-style: none;
  }
  .sp-dropdown-content ul li {
    cursor: pointer;
    white-space: pre;
  }
  .sp-dropdown-content ul li:hover {
    color: #e40000;
  }
</style>