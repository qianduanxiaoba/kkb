<template>
    <div>
        <label v-if="label">{{label}}</label>
        <slot></slot>
        <p v-if="error">{{error}}</p>
        {{form.rules}}
    </div>
</template>

<script>
    export default {
        name: "KFormItem",
        inject:["form"],
        props:{
            label :{
                type:String
            }
        },
        data(){
            return {
                error:""
            }
        }
    }
</script>

<style scoped>

</style>