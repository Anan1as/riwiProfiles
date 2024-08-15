<template>
    <button 
        class="changePageButtons p-20"
        :class="{ buttonclicked: isSelected }"
        @click="handleClick"
    >
        <img class="iconButton" :src="props.src" alt="">
        <span class="iconName">{{ props.name }}</span>
    </button>
</template>

<style lang="scss" scoped>
    .changePageButtons {
        display: flex;
        align-items: center;
        justify-content: center;
        height: 40px;
        background-color: transparent;
        border: none;
        cursor: pointer;
    }

    .iconButton {
        width: 20px;
        height: 20px;
        margin-right: 10px;
    }

    .iconName {
        font-size: 14px;
        font-weight: bold;
    }

    .buttonclicked {
        background-color: #7367ef;
        box-shadow: #7267ef6a 2px 2px 2px 2px;
        color: #fff;
        border-radius: 8px;
    }
</style>

<script setup lang="ts">
    interface IProps {
        src: string;
        name: string;
        isSelected: boolean;
    }

    const props = defineProps<IProps>();

    const emit = defineEmits(['changePage']);

    const handleClick = () => {
        emit('changePage', props.name);
    };
</script>