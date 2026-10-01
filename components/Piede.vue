<script setup lang="ts">
import logo from '../assets/itadinfo-notag.svg'

export interface PiedeProps {
    position?: 'center' | 'left' | 'right'
}

const props = withDefaults(defineProps<PiedeProps>(), {
    position: 'center',
})
</script>

<template>
    <div class="footer-container" :class="`footer-${props.position}`">
      <div class="logo-itadinfo">
        <img :src="logo" alt="Logo ITADINFO">
      </div>
    </div>
</template>

<style lang="css" scoped>
.footer-container {
    position: absolute;
    bottom: 1.25rem;
    z-index: 50;
}

.footer-center {
    left: 0;
    right: 0;
    text-align: center;
}

.footer-left {
    left: 1.25rem;
}

.footer-right {
    right: 1.25rem;
}

.logo-itadinfo {
    background-size: contain;
    background-repeat: no-repeat;
    background-position: center;
    display: block;
    height: 1em;
    width: 10em;
    margin-inline: auto;
}

.logo-itadinfo img {
    display: block;
    height: 100%;
    width: 100%;
    object-fit: contain;
}

@media print {
    .footer-container {
      position: fixed !important;
      bottom: 1.25rem;
    }

    .footer-center {
      left: 0;
      right: 0;
    }

    .footer-left {
      left: 1.25rem;
    }

    .footer-right {
      right: 1.25rem;
    }
}
</style>
