<template>
  <label> &lt;{{ content }} /&gt; </label>
</template>

<script>
export default {
  name: "InputHeader",
  props: {
    content: { type: String, required: true },
  },
};
</script>

<style>
label {
  font-size: 14px;
  color: #333333;
}
</style>