<template>
  <div class="btn" :class="clazz" @click="click">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'TikButton',
  props: {
    type: {
      type: String,
      default: 'default'
    },
    inline: {
      type: Boolean,
      default: false
    },
    size: {
      type: String,
      default: 'default'
    }
  },
  data() {
    return {
      clazz: {
        'btn-inline': this.inline,
        [`btn-${this.type}`]: true,
        [`btn-${this.size}`]: true
      }
    }
  },
  methods: {
    click: function () {
      this.$emit('click')
    }
  }
}
</script>

<style scoped>
  .btn-group {
    padding: 5px;
  }
  .btn-group .btn {
    margin: 9px;
  }

  .btn {
    display: inline-block;
    padding: 10px 20px;
    line-height: 1;
    white-space: nowrap;
    background-color: var(--grey);
    color: #ffffff;
    cursor: pointer;
    box-sizing: border-box;
    border-radius: 4px;
    user-select: none;
    text-align: center;
  }

  .btn-small {
    padding: 5px 10px;
    font-size: 12px;
  }

  .btn-inline {
    display: block;
  }

  /*.btn:hover {*/
  /*    background-color: var(--grey-dark);*/
  /*}*/

  .btn:active {
    background-color: var(--grey-dark);
  }

  .btn.shadow {
    box-shadow: 1px 1px 2px #efefef;
  }

  .btn-primary {
    background-color: var(--blue);
  }

  .btn-primary:active {
    background-color: var(--blue-dark);
  }

  .btn-success {
    background-color: var(--green);
  }

  /*.btn-success:hover {*/
  /*    background-color: var(--green-dark);*/
  /*}*/
  .btn-success:active {
    background-color: var(--green-dark);
  }

  .btn-warn {
    background-color: var(--red);
  }
  .btn-warn:active {
    background-color: var(--red-dark);
  }

</style>
