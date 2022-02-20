<template>
    <p>{{props.msg}}</p>
    <button @click="handleClick">点我</button>
    <p>{{count}} {{user.name}}</p>
    <button @click="increment">点击我count增加</button>
    <p v-for="(item,index) in arr" :key="index">{{item}}</p>
</template>
<script  setup lang="ts">
    import { ref, reactive } from 'vue'

    const count = ref(0)
    const user = reactive({name:'张三'})
    const arr = reactive([1,2,3,4])

    // 父传子
    const props = defineProps({
        msg:{
            type:String,
            default:()=>'默认值'
        }
    })

    // 子传父
    const emit = defineEmits(['on-change'])
    const handleClick = ()=>{
        emit('on-change','父组件方法被调用了')
    }

    const childNode = ()=>{
        console.log('我是childNode 子组件方法被调用了')
    }
    defineExpose({
        demo:'我是dmeo',
        child: '我是暴露的子组件',
        childNode
    })

    const increment = ()=>{
        count.value++,
        user.name='李四'
    }


</script>