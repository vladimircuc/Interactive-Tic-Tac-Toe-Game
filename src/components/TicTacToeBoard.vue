<template>
    <div class="board">
      <Cell 
        v-for="(value, index) in board" 
        :key="index" 
        :value="value" 
        @clicked = "manageClick(index)"
      />
    </div>
  </template>
  
  <script>
  import Cell from './Cell.vue';
  
  export default {
    
    props:['board', 'isFirstPlayer'],

    components: {
      Cell,
    },
    methods:{
        manageClick(key){
            var val = this.isFirstPlayer ? 'X' : 'O'
            this.board[key] = val  
            this.checkWinner()

            this.$emit('changePlayer')
        },
        checkWinner() {
            const winningCombinations = [
            [0, 1, 2], 
            [3, 4, 5], 
            [6, 7, 8], 
            [0, 3, 6], 
            [1, 4, 7], 
            [2, 5, 8], 
            [0, 4, 8], 
            [2, 4, 6], 
            ];

            for (let combination of winningCombinations) {
              const [a, b, c] = combination;

              if (this.board[a] && this.board[a] === this.board[b] && this.board[a] === this.board[c]) {
                this.$emit('won', this.board[a])
              }

              if(!this.board.includes(''))
              {
                this.$emit('won', ' ')
              }
            }

        },
    }
  };
  </script>
  
  <style scoped>
.board {
  display: grid;
  grid-template-columns: repeat(3, 100px); 
  grid-gap: 10px; 
  margin: 20px auto;
}
</style>
  