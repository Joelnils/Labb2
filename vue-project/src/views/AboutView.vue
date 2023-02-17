<script setup>
import AboutHero from "../components/AboutHero.vue";
import RichardForm from "../components/RichardForm.vue";
</script>

<template>
  <AboutHero />
  <div>
    <h2 class="bakis">Är du bakis?</h2>
    <RichardForm buttonType="Ja" />
    <RichardForm buttonType="Nej" />
  </div>
</template>
<style scoped>
.bakis {
  position: absolute;
  top: 40%;
  left: 48%;
  transform: translate(-50%, -50%);
  font-family: "Montserrat", sans-serif;
  color: white;
  padding: 12px 24px;
  border: none;
  font-size: 24px;
  font-weight: bold;
  cursor: pointer;
}
</style>
