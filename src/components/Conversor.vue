<template>
  <div class="left-aligned">
    <h1>Conversor de Temperatura</h1>
    <hr>

    <label for="celcius">Ingrese Temperatura °C :</label>
    <input id="celcius" class="form-control" v-model="celsius" type="number" />

    <br> <br>
    <label>Conversion de temperatura °F :</label>
    <label :style="{ color: getColor }">{{ convertToCelsiusToFahrenheit }}</label>
    <br> <br>
    <label>Conversion de temperatura °K :</label>
    <label :style="{ color: getColor }">{{ convertToCelsiusToKelvin }}</label>
    <br />
    <br />
    <hr>
    <p><strong>Pregunta 1/5</strong>
      Como es la forma reducida de v-on:click?
      a) v-on@click
      b) #click
      c) @click
      d) :click
      e) v-bind#click
      <br>
      <br>
      <strong>Pregunta 2/5</strong>
      vue create se utiliza para:
      a) Crear un componente Vue
      b) Crear un proyecto base Vue basado en Vue CLI
      c) Instalar Vue CLI
      d) Instalar una dependencia
      <br>
      <br>
      <strong>Pregunta 3/5</strong>
      El modificador trim recorta...
      a) Los espacios puestos adelante en una entrada de texto
      b) Los espacios puestos atrás en una entrada de texto
      c) Los espacios adelante y atrás en una entrada de texto
      d) Saca los espacios intermedios puestos en una entrada de texto
      <br>
      <br>
      <strong>Pregunta 4/5</strong>
      La propiedad routes en la definición del router de Vue.js tiene como función:
      a) Definir el path y el componente activo para esa ruta
      b) Define la barra de navegación a utilizar
      c) Define sólo todos los componentes activos en el router
      d) Definir el modo de trabajo de las rutas
      <br>
      <br>
      <strong>Pregunta 5/5</strong>
      Las mutaciones contienen...
      a) Módulos de Vuex
      b) La lógica para cambiar el estado global de la aplicación
      c) Lógica sincrónica
      d) Lógica asincrónica
    </p>
    <hr>
    <h2>Respuestas: </h2>
    <p>1C,2B,3C,4A,5B</p>
  </div>
</template>

<script>
export default {
  name: 'src-components-conversor',
  props: [],
  data() {
    return {
      celsius: null,
    };
  },
  computed: {
    convertToCelsiusToFahrenheit() {
      if (this.celsius === null) {
        return;
      }
      return (this.celsius * 9 / 5 + 32).toFixed(2);
    },
    convertToCelsiusToKelvin() {
      if (this.celsius === null) {
        return;
      }
      return (Number(this.celsius) + 273.15).toFixed(2);
    },
    getColor() {
      if (this.celsius <= 0) {
        return 'blue';
      } else if (this.celsius >= 0 && this.celsius < 15) {
        return 'magenta';
      } else {
        return 'red';
      }
    },
  },
};
</script>

<style scoped>
.left-aligned {
  text-align: left;
}
</style>
