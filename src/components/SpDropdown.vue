<template>
  <div class="sp-dropdown">
    <div class="sp-dropdown-title" @click="changeStatus()">{{ title }}</div>
    <div class="sp-dropdown-content" v-if="status">
      <ul>
        <li
          v-for="item in list"
          :key="item.value"
          :data-id="item.value">
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
      status: false
    }
  },
  props: {
    title: String,
    list: Array
  },
  methods: {
    changeStatus() {
      this.status = !this.status;
    }
  }
}
</script>

<style>
  .sp-dropdown {
    border: 1px solid #ddd;
    padding: 10px 15px;
  }
  .sp-dropdown-title {
    font-size: 20px;
    cursor: pointer;
  }
  .sp-dropdown-content ul {
    padding: 0;
    list-style: none;
  }
</style>