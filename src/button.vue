<template>
  <button class="n-button" :class="{[`icon-${iconPosition}`]: true}">
    <!-- <n-icon v-if="icon" :icon-name="icon"></n-icon> -->
    <div class="content">
      <slot></slot>
    </div>
  </button>
</template>

<script>
export default {
  name: "n-button",
  props: {
    icon: {},
    iconPosition: {
      type: String,
      default: 'left',
      validator(value) {
        return value == 'left' || value == 'right'
      }
    }
  }
};
</script>
  
<style lang="scss" scoped>
.n-button {
  height: var(--button-height);
  font-size: var(--font-size);
  padding: 0 1em;
  border-radius: var(--border-radius);
  border: 1px solid var(--border-color);
  background: var(--button-bg);
  display: inline-flex;
  justify-content: center;
  align-items: center;
  vertical-align: middle;
  &.icon-left {
    >.icon {
      order: 1;
    }
    >.content {
      order: 2;
    }
  }
  &.icon-right {
    > .icon {
      order: 2;
    }
    >.content {
      order: 1;
    }
  }
  > .icon {
    vertical-align: middle;
    order: 1;
  }
  > .content {
    padding-left: .2em;
    padding-right: .2em;
  }
  &:hover {
    border-color: var(--border-color-hover);
  }
  &:active {
    background-color: var(--button-active-bg);
  }
  &:focus {
    outline: none;
  }
}
</style>
