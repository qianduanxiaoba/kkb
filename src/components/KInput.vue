<template>
    <div>
        <input  :value="value" @input="handleInput" v-bind="$attrs">
    </div>
</template>

<script>
    export default {
        inheritAttrs:false,
        name: "KInput",
        props:{
          value: {
              type:String
,              default(){
                    return ""
              }
          }
        },
        data(){
            return {

            }
        },
        methods:{
            handleInput(e){
                this.$emit("input",e.target.value,555)
            }
        }

    }
</script>

<style scoped>

</style>