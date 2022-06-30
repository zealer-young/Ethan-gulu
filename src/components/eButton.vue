<template>
  <button class="e-button" :class="{[`icon-${iconPosition}`]: true}" @click="$emit('click')">
    <e-icon class="icon" v-if="icon && !loading" :name="icon" ></e-icon>
    <e-icon class="loading icon" name="loading" v-if="loading"></e-icon>
    <div class="content">
      <slot></slot>
    </div>
  </button>
</template>

<script>
import eIcon from '@/components/eIcon'

export default {
  name: 'e-button',
  props: {
    icon: {},
    loading: {
      type: Boolean,
      default: false
    },
    iconPosition: {
      type: String,
      default: 'left',
      validator: function (value) {
        return value === 'left' || value === 'right'
      }
    }
  },
  components: {
    eIcon
  }
}
</script>

<style lang="scss">
@keyframes spin {
  0% {
    transform: rotate(0deg);
  }
  25% {
    transform: rotate(90deg);
  }
  50% {
    transform: rotate(180deg);
  }
  75% {
    transform: rotate(270deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

.e-button {
  font-size: var(--font-size);
  height: var(--button-height);
  border-radius: var(--border-radius);
  border: 1px solid var(--border-color);
  padding: 0 1em;
  background: var(--button-background);
  vertical-align: middle;
  display: inline-flex;
  justify-content: center;
  align-items: center;

  &:hover {
    border-color: var(--border-color-hover);
  }

  &:active {
    background-color: var(--button-active-bg);
  }

  &:focus {
    outline: none;
  }

  > .content {
    order: 2
  }

  > .icon {
    order: 1;
    margin-right: .1em;
  }

  &.icon-right {
    > .content {
      order: 1
    }

    > .icon {
      order: 2;
      margin-left: .1em;
      margin-right: 0
    }
  }

  .loading {
    animation: spin 1.5s infinite linear;
  }
}
</style>
