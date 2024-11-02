<template>
  <input
    type="checkbox"
    :value="isChecked"
    @change="handleCheckBoxClick"
    :disabled="isChecked"
  /><span class="listItemText" :class="{ done: isChecked === true }">{{
    listItemText
  }}</span>
</template>
<script>
export default {
  props: ["listItemText"],
  data() {
    return {
      isChecked: false,
    };
  },
  methods: {
    handleCheckBoxClick() {
      this.isChecked = !this.isChecked;
    },
  },
};
</script>
<style>
.done {
  text-decoration: line-through;
}
</style>