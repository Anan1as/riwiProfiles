<template>
    <div class="sideBar">
        <div>
            <img class="logo" :src="logoImg" alt="">
        </div>
        <div class="container-buttons">
            <ButtonIcons
                v-for="(iterator, index) in sidebarIcons"
                :key="index"
                :icon="iterator.icon"
            />
        </div>
    </div>
</template>

<style lang="scss" scoped>
    .sideBar {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        width: 60px;
        height: 100vh;
        background-color: #fff;
        box-shadow: 1px 1px 1px rgba(0, 0, 0, 0.1);
    }

    .logo {
        margin-bottom: 15px;
        width: 30px;
        height: 30px;
    }

    .container-buttons {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
    }
</style>

<script setup lang="ts">
    import logoImage from '@/assets/images/purpleHeart.png'
    import casaIcon from '@/assets/images/casa.png'
    import archivosIcon from '@/assets/images/archivos.png'
    import carritoDeComprasIcon from '@/assets/images/carritoDeCompras.png'
    import birreteIcon from '@/assets/images/birrete.png'
    import camionIcon from '@/assets/images/camion.png'
    import sobreIcon from '@/assets/images/sobre.png'
    import globosDeTextoIcon from '@/assets/images/globosDeTexto.png'
    import calendarioIcon from '@/assets/images/calendario.png'
    import graficaIcon from '@/assets/images/grafica.png'
    import hojaLlenaIcon from '@/assets/images/hojaLlena.png'
    import usuarioIcon from '@/assets/images/usuario.png'
    import candadoIcon from '@/assets/images/candado.png'
    import hojaEnBlancoIcon from '@/assets/images/hojaEnBlanco.png'
    import escudoIcon from '@/assets/images/escudo.png'
    import tresPuntosIcon from '@/assets/images/tresPuntos.png'
    import cuadradoIcon from '@/assets/images/cuadrado.png'
    import letraAIcon from '@/assets/images/letraA.png'
    import consolaIcon from '@/assets/images/consola.png'

    const logoImg = logoImage;

    import ButtonIcons from '@/components/ButtonIcons.vue'

    // Array of sidebar items
    const sidebarIcons = [
        {
            icon: casaIcon,
        },
        {
            icon: archivosIcon,
        },
        {
            icon: carritoDeComprasIcon,
        },
        {
            icon: birreteIcon,
        },
        {
            icon: camionIcon,
        },
        {
            icon: sobreIcon,
        },
        {
            icon: globosDeTextoIcon,
        },
        {
            icon: calendarioIcon,
        },
        {
            icon: graficaIcon,
        },
        {
            icon: hojaLlenaIcon,
        },
        {
            icon: usuarioIcon,
        },
        {
            icon: candadoIcon,
        },
        {
            icon: hojaEnBlancoIcon,
        },
        {
            icon: escudoIcon,
        },
        {
            icon: tresPuntosIcon,
        },
        {
            icon: cuadradoIcon,
        },
        {
            icon: letraAIcon,
        },
        {
            icon: consolaIcon,
        }
    ]
</script>