<script setup>
import { ref } from 'vue';

const email = ref('');
const password = ref('');
const showPassword = ref(false);

const highlightInput = (event) => {
  event.target.style.outlineColor = '#4CAF50';
};

const removeHighlight = (event) => {
  event.target.style.outlineColor = '#555454';
};

const togglePasswordVisibility = () => {
  showPassword.value = !showPassword.value;
};
</script>

<template>
  <div>
    <form>
      <label for="email">Email:</label>
      <input
        v-model="email"
        @focus="highlightInput"
        @blur="removeHighlight"
        type="email"
        id="email"
        name="email"
        required
      />
      <label for="password">Password:</label>
      <input
        v-model="password"
        @focus="highlightInput"
        @blur="removeHighlight"
        :type="showPassword ? 'text' : 'password'"
        id="password"
        name="password"
        required
      />
      <button @click="togglePasswordVisibility" type="button">
        Toggle Password Visibility
      </button>
    </form>
  </div>
</template>

<style>
form {
  width: 300px;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

input {
  width: 100%;
  padding: 10px;
  margin-bottom: 15px;
  box-sizing: border-box;
  outline: 2px solid #555454;
  border-radius: 4px;
  border: none;
  margin-top: 5px;
}

button {
  background-color: #4caf50;
  color: white;
  padding: 10px 15px;
  border-radius: 4px;
  cursor: pointer;
  /* outline: 2px solid green; */
}
</style>
