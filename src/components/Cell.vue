<template>
  <div 
    class="cell d-flex justify-content-center align-items-center border" 
    :class="{ 'cell-x': value === 'X', 'cell-o': value === 'O' }"
    @click="buttonClicked"
  >
    {{ value }}
  </div>
</template>

  
  <script>
  export default {
  props: ['value'],
  methods: {
    buttonClicked() {
      if (this.value === '') {
        this.$emit('clicked');
      }
    },
  },
};

  </script>
  
  <style scoped>
.cell {
  width: 100px;
  height: 100px;
  font-size: 2.5rem; /* Larger font size for better visibility */
  font-weight: bold; /* Bold text for X and O */
  cursor: pointer;
  background-color: #f8f9fa; /* Light gray background */
  border: 2px solid #333; /* Darker border */
  border-radius: 5px; /* Slightly rounded corners */
  transition: background-color 0.3s, box-shadow 0.3s, transform 0.2s;
  text-transform: uppercase; /* Ensure X and O are always uppercase */
  display: flex;
  justify-content: center;
  align-items: center;
}

/* Hover effect for the cell */
.cell:hover {
  background-color: #e0e0e0;
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
  transform: scale(1.05); /* Slight zoom effect */
}

/* Styling for X */
.cell-x {
  color: #007bff; /* Blue color for X */
  background-color: rgba(0, 123, 255, 0.1); /* Light blue background for X */
}

/* Styling for O */
.cell-o {
  color: #dc3545; /* Red color for O */
  background-color: rgba(220, 53, 69, 0.1); /* Light red background for O */
}
</style>
