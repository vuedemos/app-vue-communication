<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <div>
      <button @click="show" class="btn btn-primary">打开模态框</button>
    </div>
    <Modal 
      :show="isShow" 
      :modal-title="modalTitle" 
      :modal-content="modalContent" 
      :secondary-button-content="secondaryButtonContent"
      :primary-button-content="primaryButtonContent"
      @on-save="save"
      @on-close="close"
      ></Modal>
    <ModalBackdrop :show="isShow" @on-close="close"></ModalBackdrop>
  </div>
</template>

<script>
import ModalBackdrop from './components/ModalBackdrop'
import Modal from './components/Modal'

export default {
  name: 'app',
  components: {
    ModalBackdrop,
    Modal
  },
  methods: {
    show () {
      this.isShow = true
      console.log('show():关闭模态框')
    },
    close () {
      this.isShow = false
      console.log('close():关闭模态框')
    },
    save () {
      this.isShow = false
      console.log('save():保存内容')
    }
  },
  data () {
    return {
      isShow: false,
      modalTitle: '我是模态框标题',
      modalContent: '我是模态框内容',
      secondaryButtonContent: '关闭',
      primaryButtonContent: '保存'
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

.btn {
    -webkit-appearance: button;
    display: inline-block;
    font-weight: 400;
    text-align: center;
    white-space: nowrap;
    vertical-align: middle;
    user-select: none;
    border: 1px solid transparent;
    padding: .375rem .75rem;
    font-size: 1rem;
    line-height: 1.5;
    border-radius: .25rem;
    transition: color .15s ease-in-out,background-color .15s ease-in-out,border-color .15s ease-in-out,box-shadow .15s ease-in-out;
}

.btn-primary {
    color: #fff;
    background-color: #007bff;
    border-color: #007bff;
}


.btn-primary:hover {
    color: #fff;
    background-color: #0069d9;
    border-color: #0062cc;
}

.btn:not(:disabled):not(.disabled) {
    cursor: pointer;
}


.btn-primary:not(:disabled):not(.disabled):active {
    color: #fff;
    background-color: #0062cc;
    border-color: #005cbf;
}

.btn-primary:not(:disabled):not(.disabled):active:focus {
    box-shadow: 0 0 0 0.2rem rgba(0,123,255,.5);
}
</style>
