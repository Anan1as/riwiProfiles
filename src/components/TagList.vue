<template>
    <div class="tags-container">
        <span 
            v-for="tag in tags" 
            :key="tag.name" 
            class="tag"
            :style="{ color: tag.color, backgroundColor: tag.background }">
            {{ tag.name }}
        </span>
    </div>
</template>

<style lang="scss" scoped>
    .tags-container {
        display: flex;
        flex-wrap: wrap;
        margin-top: 20px;
    }

    .tag {
        padding: 5px 10px;
        margin-right: 5px;
        margin-bottom: 5px;
        border-radius: 5px;
        font-size: 14px;
        font-weight: bold;
    }
</style>

<script setup lang="ts">
    interface ITag {
        name: string;
        color: string;
        background: string;
    }

    const props = defineProps<{
        tags: ITag[]
    }>();
</script>