<template>
    <div>
        <slot>

        </slot>
    </div>
</template>

<script>
    export default {
        name: "KForm",
        provide(){
          return{
              form:this
          }
        },
        props:{
            model:{
                type:Object,
                required:true
            },
            rules:{
                type: Object,
                default() {
                    return {};
                }
            }
        }
    }
</script>

<style scoped>

</style>