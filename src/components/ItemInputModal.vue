<template>
  <div class="backdrop">
    <div class="modal">
      <h3>Enter your task:</h3>
      <input type="text" ref="taskInput" />
      <button @click="handleAddToListClick" class="add-button">Add to list</button>
    </div>
  </div>
</template>
<script>
export default {
   

  methods: {

    handleAddToListClick() {
      const input = this.$refs.taskInput;
      this.$emit("passInput", input.value)
    },
  },
};
</script>
<style>
.backdrop {
  top: 0%;
  left: 0%;
  width: 100%;
  height: 100%;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  align-items: center;
  justify-content: center;
}

.modal {
  margin: 0 auto;
  width: 300px;
  height: 100px;
  border: 1px solid black;
  background: white;
  padding: 10px;
  border-radius: 10px;
}
</style>