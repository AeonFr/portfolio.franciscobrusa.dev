<template>
  <negate-container class="flex-ns items-start ph2 p15-ns">
    <article class="mh3">
      <h1>Timekr: Aplicación de gestión de tiempo</h1>

      <p>
        <a href="https://timekr.netlify.com" target="_blank">Timekr</a>
        es una aplicación web para medir el tiempo por proyecto,
        usando la técnica “Pomodoro”
        (divide el tiempo en segmentos de 25 minutos,
        con descansos de 5 a 20 minutos entre medio).
      </p>
    </article>
    <img src="~/assets/portfolio/timekr.jpg" alt="Captura de pantalla de Timekr" />
  </negate-container>
</template>

<script>
import NegateContainer from "~/components/negateContainer.vue";
export default {
  components: { NegateContainer }
};
</script>