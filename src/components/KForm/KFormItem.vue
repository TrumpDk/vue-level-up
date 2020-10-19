<template>
  <div>
    <!-- label -->
    <label v-if="label">{{ label }}</label>
    <slot></slot>
    <p v-if="error">{{ error }}</p>
  </div>
</template>

<script>
import Schema from "async-validator";
export default {
  inject: ["form"],
  data() {
    return {
      error: "", // error是空说明校验通过
    };
  },
  props: {
    label: {
      type: String,
      default: "",
    },
    prop: {
      type: String,
    },
  },
  mounted() {
    this.$on("validate", () => {
      this.validate();
    });
  },
  methods: {
    validate() {
      // rules
      const rules = this.form.rules[this.prop];
      // value
      const value = this.form.model[this.prop];

      // validate desc
      const desc = { [this.prop]: rules };
      console.log("desc", desc, "value", value);

      const schema = new Schema(desc);

      return schema.validate({ [this.prop]: value }, (errors) => {
        if (errors) {
          console.log("ssss");
          this.error = errors[0].message;
        } else {
          // 校验通过
          this.error = "";
        }
        console.log("hi there", errors);
      });
    },
  },
};
</script>

<style lang="css" scoped></style>
