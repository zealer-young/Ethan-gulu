<template>
  <div id="app">
    <e-Button iconPosition="right" :style="{marginRight:'10px'}">按钮</e-Button>
    <e-button-group>
      <e-Button icon="left-square">上一页</e-Button>
      <e-button>中间</e-button>
      <e-Button icon="right-square" iconPosition="right">下一页</e-Button>
    </e-button-group>
  </div>
</template>

<script>
import eButton from './components/eButton.vue'
import eButtonGroup from './components/eButton-group.vue'

export default {
  name: 'App',
  components: {
    eButton,
    eButtonGroup
  },
  data() {
    return {
      loading: false
    }
  }
}
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  margin: 20px;
  font-size: var(--font-size);
  --button-height: 32px;
  --font-size: 14px;
  --button-bg: white;
  --button-active-bg: #eee;
  --border-radius: 4px;
  --color: #333;
  --border-color: #999;
  --border-color-hover: #666;
}
</style>
