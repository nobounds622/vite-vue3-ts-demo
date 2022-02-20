<script setup lang="ts">
  import HelloWorld from './components/HelloWorld.vue'
  import TestPropsEmit from './components/test-props-emit/index.vue';
  import { ref, onMounted} from 'vue';
  const msg = ref('hello world')
  const handleChange = (params:string)=>{
    console.log('params',params)
  }
  const propsEmitRef = ref()
  onMounted(()=>{
    console.log('value',propsEmitRef.value)
  })
</script>

<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <TestPropsEmit ref="propsEmitRef" :msg="msg" @on-change="handleChange"></TestPropsEmit>
  <!-- <HelloWorld msg="Hello Vue 3 + TypeScript + Vite" /> -->
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
