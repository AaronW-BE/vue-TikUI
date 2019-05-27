<template>
  <div id="app">
    <button-group>
      <tik-button type="warn" size="small">删除</tik-button>
      <tik-button type="success" size="default" @click="clickBtn">弹出</tik-button>
    </button-group>
    <tik-modal tips="Tips" :show.sync="show" @confirm-click="click">
      Hello, Are you ok ? <br/>
      Hello, Are you ok ? <br/>
      Hello, Are you ok ? <br/>
      Hello, Are you ok ? <br/>
      Hello, Are you ok ? <br/>
      Hello, Are you ok ? <br/>
      Hello, Are you ok ? <br/>
      Hello, Are you ok ? <br/>
    </tik-modal>
  </div>
</template>

<script>
import TikButton from "./components/TikButton/TikButton";
import ButtonGroup from "./components/TikButton/ButtonGroup";
import TikModal from "./components/TikModal/TikModal";
export default {
  name: 'app',
  components: {TikModal, ButtonGroup, TikButton},
  data() {
    return {
      show: true
    }
  },
  methods: {
    click() {
      this.show = false;
    },
    clickBtn() {
      this.show = true;
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
