<template>
    <div class="containerComponents">
        <CardConnectionComponent
            v-for="connection in connections"
            :key="connection.name"
            :profilePicture="connection.profilePicture"
            :name="connection.name"
            :rol="connection.rol"
            :tags="connection.tags"
            :projects="connection.projects"
            :taks="connection.tasks"
            :connections="connection.connections"
            :iconConnection="connection.iconConnection"
            :ConnectionStatus="connection.ConnectionStatus"
        />
    </div>
</template>

<script setup lang="ts">
    import { onMounted, ref } from 'vue';
    import CardConnectionComponent from '@/components/CardConnection.vue';

    import profilePicture1 from '@/assets/images/profilePictures/profilePicture1.png';
    import profilePicture2 from '@/assets/images/profilePictures/profilePicture2.png';
    import profilePicture3 from '@/assets/images/profilePictures/profilePicture3.png';
    import profilePicture4 from '@/assets/images/profilePictures/profilePicture4.png';
    import profilePicture5 from '@/assets/images/profilePictures/profilePicture5.png';
    import profilePicture6 from '@/assets/images/profilePictures/profilePicture6.png';
    import usuarioActivoIcon from '@/assets/images/usuarioActivo.png';

    interface Connection {
        profilePicture: string;
        name: string;
        rol: string;
        tags: Array<{ name: string; color: string; background: string }>;
        projects: string | number;
        tasks: string | number;
        connections: string | number;
        iconConnection: string;
        ConnectionStatus: string;
    }


    const connections = ref<Connection[]>([]);

    onMounted(() => {
        fetchData();
    });

    async function fetchData() {
        try {
            const response = await fetch('/users.json');
            if (!response.ok) {
                throw new Error('Network response was not ok');
            }
            const text = await response.text();
            const data = JSON.parse(text);
            connections.value = data;
        } catch (error) {
            console.error('There was a problem with the fetch operation:', error);
        }
    }

</script>

<style lang="scss" scoped>
    .containerComponents {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
    }
</style>