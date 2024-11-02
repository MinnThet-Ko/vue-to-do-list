<template>
    <div >
      <h1>To-do list</h1>
      <hr />
      <div class="list-container">
      <div v-for="(item, index) in listItems" v-bind:key="index" class="list-item">
        <div>
          <ListItem :listItemText="item"/>
        </div>
     
      </div>
      <button @click="handleAddItemClick" class="add-button">
        Add new item
      </button>
      <div v-if="showInputModal">
        <ItemInputModal  @passInput="handlePassInput"/>
      </div>
    </div>
    </div>
  </template>
  
  <script>
import ItemInputModal from './ItemInputModal.vue';
import ListItem from './ListItem.vue';


  
  export default {
    name: "App",
    data() {
      return {
        listItems: [
          "Do the laundry",
          "Go groccery shopping",
          "Finish the English assignment.",
        ],
        showInputModal: false,
      };
    },
    components:{
      ListItem,
      ItemInputModal
    },
    methods: {
      handleAddItemClick(){
        this.showInputModal = !this.showInputModal
      },
      handlePassInput(inputTask){
        this.showInputModal = false
        this.listItems.push(inputTask)
      }
    }
  };
  </script>
  
  <style>
  
  .list-container {
    text-align: left;
    margin: 0 auto;
    border: 2px solid black;
    padding: 10px;
    border-radius: 10px;
    width: 30%;
  }
  
  .list-item {
    margin: 5px;
  }
  .add-button {
    border: 1px solid gray;
    height: 20px;
    border-radius: 5px;
    background: white;
    margin: 5px;
  }
  </style>
  