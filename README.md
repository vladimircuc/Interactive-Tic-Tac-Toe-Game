# Interactive Tic-Tac-Toe Game 

This is a fully interactive Tic Tac Toe Game built using Vue.js 3. The project demonstrates modern frontend development practices, including component-based architecture, props, event handling, and reactivity. It’s designed with Bootstrap 5 for responsive and visually appealing styling.    

## Technologies Used   
 
- Vue.js 3: For building the interactive user interface and managing state reactivity.   
- Bootstrap 5: For responsive and modern styling.   
- JavaScript (ES6): For handling game logic and events.   

## How It Works  
  
### Gameplay:   
Players click on cells to make their move.   
The game ensures that players alternate correctly and that moves can’t overwrite existing ones.   

### Winner Detection:    
Checks all possible winning combinations after each move.       
Displays a modal with the winner or a draw message.    

### Restart Option:    
After the game ends, the modal provides an option to reset the game.   

## Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur).

## Customize configuration

See [Vite Configuration Reference](https://vite.dev/config/).

## Project Setup

```sh
git clone https://github.com/your-username/tic-tac-toe.git
```

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```
