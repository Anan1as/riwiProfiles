<template>
    <button class="btnIcons p-5">
        <img :src="props.icon" alt="">
    </button>
</template>

<style lang="scss" scoped>
    .btnIcons {
        background-color: transparent;
        border: none;
        cursor: pointer;

        img {
            width: 20px;
            height: 20px;
        }
    }

    .btnIcons:hover {
        background-color: #e1e1e1;
        border-radius: 5px;
    }
</style>

<script setup lang="ts">
    interface IProps {
        icon: string;
    }

    const props = defineProps<IProps>();
</script>