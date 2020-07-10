<template>
  <div>
    <el-input
      ref="input"
      v-bind="$attrs"
      v-on="$listeners"
      class="e-input"
      :value="value"
      @input="$emit('input', $event)"
    ></el-input>
  </div>
</template>

<script>
export default {
  inheritAttrs: false,
  name: "KInput",
  props: {
    value: {
      type: String,
      required:true
    },
    limit:{
        type:Number,
        default:0
    },
    type:{
        type:String,
    }
  },
  mounted(){
      if(this.type==="number"){
        let input =  this.$refs.input.$refs.input;
        input.addEventListener("input",function(e){
              e.target.value = e.target.value.replace(/[^0-9.]/g,'')
          })
        input.addEventListener("blur",(e)=>{
           if(e.target.value){
              e.target.value = parseFloat(e.target.value).toFixed(this.limit)
           }
        })
      }
  },
  data() {
    return {

    };
  },
  methods: {
      
  }
};
</script>

<style scoped>
</style>