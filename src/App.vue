<template>
    <div class="container">
        <div class="sidebar">
            <SidebarComponent />
        </div>
        <div class="leftComponent">
            <TopbarComponent />
            <BannerComponent />
            <div class="containerButtons">
                <ChangePageButtons 
                    v-for="button in buttonsData"
                    :src="button.src"
                    :name="button.name"
                    :isSelected="button.name === page"
                    @changePage="changePage"
                />
            </div>
            <div class="containerPageSelected" v-if="page === 'Profile'">
                <ProfileComponent />
            </div>
            <div class="containerPageSelected" v-if="page === 'Team'">
                <TeamComponent />
            </div>
            <div class="containerPageSelected" v-if="page === 'Projects'">
                <ProjectsComponent />
            </div>
            <div class="containerPageSelected" v-if="page === 'Connections'">
                <ConnectionsComponent />
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    .container {
        display: flex;

        .sidebar {
            position: fixed;  // Fija la barra lateral en su lugar
            top: 0;
            left: 0;
            width: 12%;
            height: 100vh;  // Asegúrate de que cubra toda la altura de la ventana
        }
        
        .leftComponent {
            display: flex;
            flex-direction: column;
            justify-content: center;
            width: 80%;
            margin-left: 12%;
            margin-top: 20px;
        }
    }

    .containerButtons {
        display: flex;
        margin-top: 20px;
    }

    .containerPageSelected {
        margin-top: 20px;
    }
</style>

<script setup lang="ts">
    import SidebarComponent from '@/components/Sidebar.vue';
    import TopbarComponent from '@/components/Topbar.vue';
    import BannerComponent from '@/components/Banner.vue';
    import ProfileComponent from '@/components/ProfileWindow.vue';
    import TeamComponent from '@/components/TeamWindow.vue';
    import ProjectsComponent from '@/components/ProjectsWindow.vue';
    import ConnectionsComponent from '@/components/ConnectionsWindow.vue';
    
    import ChangePageButtons from '@/components/ChangePageButtons.vue';

    import usuarioActivo from '@/assets/images/usuarioActivo.png';
    import pareja from '@/assets/images/pareja.png';
    import colecciones from '@/assets/images/colecciones.png';
    import conexiones from '@/assets/images/conexiones.png';

    const buttonsData = [
        {
            src: usuarioActivo,
            name: 'Profile'
        },
        {
            src: pareja,
            name: 'Team'
        },
        {
            src: colecciones,
            name: 'Projects'
        },
        {
            src: conexiones,
            name: 'Connections'
        }
    ]


    // Changing pages logic
    import { ref } from 'vue';
    const page = ref('Profile');

    const changePage = (newPage: string) => {
        page.value = newPage;
    }
</script>