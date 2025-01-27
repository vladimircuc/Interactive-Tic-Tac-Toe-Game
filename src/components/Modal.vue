<template>
    <div class="backdrop">
      <div class="custom-modal">
        <h2 v-if="winner != ' '">Congratulations!</h2>
        <p v-if="winner != ' '">{{ winner }} won the game!</p>
        <p v-if="winner == ' '">Tie! No one won the game!</p>
        <button class="action-button" @click="closeModal">Play Again</button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: ['winner'],
    methods: {
      closeModal() {
        this.$emit('restart'); 
      },
    },
  };
  </script>
  
  <style scoped>

  .backdrop {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5); /* Semi-transparent black */
    display: flex;
    justify-content: center; /* Center modal horizontally */
    align-items: center; /* Center modal vertically */
    z-index: 1000; /* Ensure it's above everything */
  }
  
  /* Modal Styling */
  .custom-modal {
    width: 400px;
    padding: 30px;
    background: #fff;
    border-radius: 12px;
    text-align: center;
    box-shadow: 0px 6px 15px rgba(0, 0, 0, 0.2);
  }
  
  /* Heading */
  .custom-modal h2 {
    font-size: 1.8rem;
    margin-bottom: 10px;
    color: #333;
  }
  
  /* Paragraph */
  .custom-modal p {
    font-size: 1.2rem;
    color: #666;
    margin-bottom: 20px;
  }
  
  /* Button Styling */
  .action-button {
    padding: 10px 20px;
    font-size: 1rem;
    color: #fff;
    background-color: #007bff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }
  
  .action-button:hover {
    background-color: #0056b3;
  }
  </style>
  