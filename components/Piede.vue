<script setup lang="ts">
import logo from '../assets/itadinfo-notag.svg'
</script>

<template>
    <div absolute bottom-5 right-0 left-0 text-center class="footer-container">
        <div class="logo-itadinfo">
          <img :src="logo" alt="Logo ITADINFO" />
        </div>
    </div>
</template>

<style lang="css" scoped>
.logo-itadinfo {
    background-size: contain;
    background-repeat: no-repeat;
    background-position: center;
    display: inline-block;
    height: 1em;
    width: 10em;
}

@media print {
  .footer-container {
    /* La proprietà position viene resettata per la stampa */
    position: static !important;
    /* Margine in alto per separare il footer dal contenuto precedente */
    margin-top: -1.5cm;
    text-align: center;
  }
}
</style>
