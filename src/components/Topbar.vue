<template>
    <div class="topbarContainer p-20">
        <div>
            <ButtonIcons :icon="busquedaIcon" />
            <input class="input" type="text" name="search" placeholder="Search..." id="">
        </div>
        <div>
            <ButtonIcons 
                v-for="icon in topbarIcons" 
                :icon="icon.icon" 
            />
            <img class="profilePicture" :src="profilePicture" alt="Profile Picture" />
        </div>
    </div>
</template>

<style lang="scss" scoped>
    .topbarContainer {
        display: flex;
        justify-content: space-between;
        align-items: center;
        height: 60px;
        width: 100%;
        background-color: #fff;
        box-shadow: 0 1px 1px rgba(0, 0, 0, 0.1);
        border-radius: 5px;

        .input {
            width: 300px;
            height: 30px;
            border: none;
            border-radius: 5px;
            padding: 5px;
            margin-left: 10px;
        }

        .profilePicture {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            margin-left: 10px;
        }

        div {
            display: flex;
            align-items: center;
        }
    }
</style>

<script setup lang="ts">
    import ButtonIcons from '@/components/ButtonIcons.vue';

    //Imports for the images
    import busquedaIcon from '@/assets/images/busqueda.png';
    import traducirIcon from '@/assets/images/traducir.png';
    import solIcon from '@/assets/images/sol.png';
    import componenteIcon from '@/assets/images/componente.png';
    import campanaIcon from '@/assets/images/campana.png';
    import profilePicture from '@/assets/images/profilePictures/profilePicture1.png';

    const topbarIcons = [
        {
            icon: traducirIcon,
        },
        {
            icon: solIcon,
        },
        {
            icon: componenteIcon,
        },
        {
            icon: campanaIcon,
        }
    ];
</script>