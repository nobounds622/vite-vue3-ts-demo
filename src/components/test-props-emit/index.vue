<template>
    <p>{{props.msg}}</p>
    <button @click="handleClick">点我</button>
</template>
<script  setup lang="ts">
    const props = defineProps({
        msg:{
            type:String,
            default:()=>'默认值'
        }
    })
    const emit = defineEmits(['on-change'])
    const handleClick = ()=>{
        emit('on-change','父组件方法被调用了')
    }
    const childNode = ()=>{
        console.log('子组件方法被调用了')
    }
    defineExpose({
        demo:'我是dmeo',
        child: '我是暴露的子组件'
    })
</script>