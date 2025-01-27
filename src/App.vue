<template>
  <header>
    <h1>Welcome To My Tic Tac Toe Game</h1>
  </header>
  <main>
    <TicTacToeBoard @changePlayer = "changePlayer" @won = "gameWon" :board="board" :isFirstPlayer="isFristPlaer"/>
    <Modal v-if="showModal" :winner="winner" @restart = "restartGame"/>

    <div class="instructions">
      <p>Click on a cell to play your move.</p>
    </div>
  </main>
</template>

<script>

import Modal from './components/Modal.vue';
import TicTacToeBoard from './components/TicTacToeBoard.vue';



export default {
  components: {
    Modal,
    TicTacToeBoard,
  },
  data() {
    return {
      showModal: false, 
      winner: '',
      board: Array(9).fill(''),
      isFristPlaer: true
    };
  },
  methods:{
    restartGame(){
      this.board = Array(9).fill('')
      this.winner = ''
      this.isFristPlaer = true
      this.showModal = false
    }, 
    gameWon(winner){
      this.winner = winner
      this.showModal = true
    },
    changePlayer(){
      this.isFristPlaer = !this.isFristPlaer
    }
  }
};
</script>

<style scoped>
header {
  text-align: center;
  margin-top: 20px;
}

h1 {
  font-size: 2.5rem;
  font-weight: bold;
  color: #333;
}

main {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh; /* Center the content */
}

.instructions {
  margin-top: 20px;
  font-size: 1rem;
  color: #666;
  text-align: center;
}
</style>
