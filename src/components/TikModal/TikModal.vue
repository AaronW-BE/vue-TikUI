<template>
  <div class="modal" :class="{show}">
    <div class="modal-container">
      <div class="modal-header">{{this.tips || '提示'}}</div>
      <div class="modal-content"><slot></slot></div>
      <div class="modal-footer">
        <button-group>
          <tik-button v-if="showCancelButton" @click.native="showModal">取消</tik-button>
          <tik-button type="success" @click.native="confirmClick">确定</tik-button>
        </button-group>
      </div>
    </div>
  </div>
</template>

<script>
import TikButton from "../TikButton/TikButton";
import ButtonGroup from "../TikButton/ButtonGroup";
export default {
  name: 'TikModal',
  components: {ButtonGroup, TikButton},
  props: {
    show: {
      type: Boolean,
      default: false
    },
    showCancelButton: {
      type: Boolean,
      default: true
    },
    tips: String
  },
  data() {
    return {
    };
  },
  methods: {
    showModal: function () {
      this.$emit('update:show', false)
    },
    confirmClick() {
      this.$emit('confirm-click');
    }
  }
}
</script>

<style scoped>

  /*modal*/
  .modal {
    display: none;
    position: fixed;
    top: 0;
    transition: all 1.3s;
  }
  .modal.show {
    display: block;
  }
  .modal::after {
    position: fixed;
    z-index: 0;
    content: '';
    left: 0;
    right: 0;
    top: 0;
    bottom: 0;
    background-color: var(--grey-dark);
    opacity: .3;
  }
  .modal * {
    position: relative;
    z-index: 999;
  }

  .modal .modal-container {
    position: fixed;
    left: 0;
    right: 0;
    top: 30%;
    margin: 0 auto;
    min-width: 300px;
    width: 30%;
    background-color: #ffffff;
    padding: 15px 15px 5px 15px;
    box-shadow: 2px 2px 5px var(--grey);
  }

  .modal-container .modal-header {
    font-weight: bold;
  }

  .modal-container .modal-content {
    padding: 15px;
    max-height: 60%;
    overflow: hidden;
  }

  .modal-container .modal-footer {
    text-align: right;
  }

</style>
