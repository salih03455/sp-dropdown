# sp-dropdown

## Installation

```
npm i sp-dropdown
```

<hr>

## Usage

```js
<template>
  <div class="container">
    <sp-dropdown
      :title=title
      :list=list
    />
  </div>
</template>
<script>
import SpDropdown from 'sp-dropdown';
export default {
  data() {
    return {
      title: 'Select Auto',
      list: [
        {
          value: 1313123,
          title: 'Mercedes'
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
      ]
    }
  },
  components: {
    SpDropdown
  }
}
</script>
```