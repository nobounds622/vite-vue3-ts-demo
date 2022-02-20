<script setup lang="ts">
  import HelloWorld from './components/HelloWorld.vue'
  import TestPropsEmit from './components/test-props-emit/index.vue';
  import { ref, reactive, onMounted } from 'vue';
  const msg = ref('hello world')
  const count = ref(0)
  const handleChange = (params:string)=>{
    console.log('params',params)
  }
  const propsEmitRef = ref()
  onMounted(()=>{
    console.log('调用子组件方法',propsEmitRef.value.childNode())
    console.log('调用子组件属性',propsEmitRef.value.demo)
  })
</script>

<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <TestPropsEmit ref="propsEmitRef" :msg="msg" @on-change="handleChange"></TestPropsEmit>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
