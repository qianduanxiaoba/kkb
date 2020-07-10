<template>
  <el-input
    ref="input"
    v-bind="$attrs"
    v-on="$listeners"
    :value="value"
    :type="type ==='number'?'text':type"
    @input="$emit('input', $event)"
  >
    <template slot="prefix">
      <slot name="prefix"></slot>
    </template>
    <template slot="suffix">
      <slot name="suffix"></slot>
    </template>
    <template slot="prepend">
      <slot name="prepend"></slot>
    </template>
    <template slot="append">
      <slot name="append"></slot>
    </template>
  </el-input>
</template>

<script>
export default {
  name: "KInput",
  props: {
    value: {
      type: String,
      required: true
    },
    limit: {
      type: Number,
      default: 0
    },
    type: {
      type: String
    }
  },
  mounted() {
    if (this.type === "number") {
      let input = this.$refs.input.$refs.input;
      input.addEventListener("input", function(e) {
        e.target.value = e.target.value.replace(/[^0-9.]/g, "");
      });
      input.addEventListener("blur", e => {
        if (e.target.value) {
          e.target.value = parseFloat(e.target.value).toFixed(this.limit);
        }
      });
    }
  },
  data() {
    return {};
  },
  methods: {}
};
</script>

<style scoped>
</style>