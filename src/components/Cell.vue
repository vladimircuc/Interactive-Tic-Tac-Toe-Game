<template>
    <div class="cell d-flex justify-content-center align-items-center border" @click="buttonClicked">
      {{ value }}
    </div>
  </template>
  
  <script>
  export default {
    props: ['value'],
    methods: {
        buttonClicked(){
            if(this.value == '')
                this.$emit('clicked')
        }
    }
  };
  </script>
  
  <style scoped>
  .cell {
    width: 100px;
    height: 100px;
    font-size: 24px;
    cursor: pointer;
    background-color: #f8f9fa;
    border: 2px solid #333;
    transition: background-color 0.3s, box-shadow 0.3s;
  }
  
  .cell:hover {
    background-color: #e0e0e0;
    box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
  }
  </style>
  