<template>
  <div id="app">
    <div class="counter-container">
      <!-- Mostrar el valor del contador -->
      <h1>Contador: {{ counter }}</h1>
      <!-- Mensaje condicional basado en el valor del contador -->
      <p v-if="counter < 0" class="negative">Número negativo</p>
      <p v-else-if="counter > 0" class="positive">Número positivo</p>
      <p v-else class="neutral">Número neutro</p>
      <!-- Botón para incrementar el contador -->
      <button class="btn increment" @click="incrementCounter">Incrementar</button>
      <!-- Botón para decrementar el contador -->
      <button class="btn decrement" @click="decrementCounter">Decrementar</button>
      <!-- Botón para reiniciar el contador a 0 -->
      <button class="btn reset" @click="resetCounter">Reiniciar</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      // Inicializar el contador con valor 0
      counter: 0
    };
  },
  methods: {
    // Método para incrementar el contador
    incrementCounter() {
      this.counter++;
    },
    // Método para decrementar el contador
    decrementCounter() {
      this.counter--;
    },
    // Método para reiniciar el contador a 0
    resetCounter() {
      this.counter = 0;
    }
  }
};
</script>

<style>
/* Estilos globales */
body {
  background: linear-gradient(135deg, #f5f7fa, #c3cfe2);
  font-family:Arial, Helvetica, sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  margin: 0;
}

/* Estilos del contenedor principal */
#app {
  text-align: center;
  margin-top: 20px;
}

/* Estilos del contenedor del contador */
.counter-container {
  background: white;
  border-radius: 10px;
  padding: 20px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  width: 300px;
}

/* Estilos del encabezado */
h1 {
  font-size: 2.5em;
  margin-bottom: 20px;
  color: #333;
}

/* Estilos de los botones */
button {
  margin: 10px;
  padding: 15px 30px;
  font-size: 18px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background 0.3s ease, transform 0.3s ease;
}

/* Estilos del botón incrementar */
button.increment {
  background: #4caf50;
  color: white;
}

button.increment:hover {
  background: #45a049;
}

/* Estilos del botón decrementar */
button.decrement {
  background: #f44336;
  color: white;
}

button.decrement:hover {
  background: #e53935;
}

/* Estilos del botón reiniciar */
button.reset {
  background: #ffffff;
  color: rgb(116, 116, 116);
}

button.reset:hover {
  transform: scale(1.1);
}

/* Estilos de los párrafos */
p {
  font-size: 1.2em;
  margin-top: 20px;
}

/* Estilos para mensajes negativos, positivos y neutrales */
p.negative {
  color: #e74c3c;
}

p.positive {
  color: #2ecc71;
}

p.neutral {
  color: #95a5a6;
}
</style>
