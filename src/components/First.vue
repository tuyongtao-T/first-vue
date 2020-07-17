<template>
    <div class="First">
        <h6>你好，现在是星期{{new Date().getDay()}}</h6>
        <p>我是{{name}},今年{{age}}岁</p>
    </div>
</template>

<script>

export default {
    props: {
        age:{
            required: true
        },
        name:{
            type: String,
        }
    },
}
</script>

<style scoped>

</style>>

