<template>
    <div class="containerCards m-1">
        <img class="profilePicture" :src="props.profilePicture" alt="">
        <h3>{{ props.name }}</h3>
        <p style="color: #9f9f9f;">{{ props.rol }}</p>
        <TagList :tags="props.tags" />
        <div class="containerInformation">
            <div>
                <p>{{ props.projects }}</p>
                <p>Projects</p>
            </div>
            <div>
                <p>{{ props.taks }}</p>
                <p>Tasks</p>
            </div>
            <div>
                <p>{{ props.connections }}</p>
                <p>Connections</p>
            </div>
        </div>
        <div class="containerButtons">
            <button :class="buttonClass" class="p-10">
                <img class="iconConnection" :src="props.iconConnection" alt="">
                <span>{{ props.ConnectionStatus }}</span>
            </button>
            <button class="btnMensaje p-10">
                <img class="iconConnection" :src="sobreIcon" alt="">
            </button>
        </div>
    </div>
</template>

<script setup lang="ts">
import { computed } from 'vue';
import TagList from '@/components/TagList.vue';
import sobreIcon from '@/assets/images/sobre.png';

interface ITag {
    name: string;
    color: string;
    background: string;
}

interface IProps {
    profilePicture: string;
    name: string;
    rol: string;
    tags: ITag[];
    projects: string | number;
    taks: string | number;
    connections: string | number;
    iconConnection: string;
    ConnectionStatus: string;
}

const props = defineProps<IProps>();

const buttonClass = computed(() => {
    return props.ConnectionStatus === 'Connect' ? 'btnConnect' : 'btnConnected';
});
</script>

<style lang="scss" scoped>
    .containerCards {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        width: 382px;
        height: 382px;
        background-color: #fff;
        border-radius: 10px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        padding: 20px;

        .profilePicture {
            width: 100px;
            height: 100px;
            border-radius: 50%;
            margin-bottom: 20px;
        }

        .containerInformation {
            display: flex;
            justify-content: space-around;
            width: 100%;
            margin-top: 20px;
            margin-bottom: 20px;

            div {
                display: flex;
                flex-direction: column;
                align-items: center;
            }
        }

        .containerButtons {
            display: flex;
            justify-content: center;
            width: 100%;

            .btnConnected {
                display: flex;
                align-items: center;
                justify-content: center;
                background-color: #7367ef;
                box-shadow: #7267ef6a 2px 2px 2px 2px;
                border: none;
                border-radius: 5px;
                cursor: pointer;
                margin-right: 15px;

                img {
                    width: 20px;
                    height: 20px;
                    margin-left: 10px;
                    margin-right: 8px;
                }

                span {
                    font-weight: bold;
                    margin-right: 10px;
                    color: #fff;
                }
            }

            .btnConnect {
                display: flex;
                align-items: center;
                justify-content: center;
                background-color: #e0e0e0;
                box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
                border: none;
                border-radius: 5px;
                cursor: pointer;
                margin-right: 15px;

                img {
                    width: 20px;
                    height: 20px;
                    margin-left: 10px;
                    margin-right: 8px;
                }

                span {
                    font-weight: bold;
                    margin-right: 10px;
                    color: #7367ef;
                }
            }

            .btnMensaje {
                display: flex;
                align-items: center;
                justify-content: center;
                background-color: #e0e0e0;
                border: none;
                border-radius: 5px;
                cursor: pointer;

                img {
                    width: 20px;
                    height: 20px;
                    margin-left: 5px;
                    margin-right: 5px;
                }
            }
        }
    }

    .iconConnection {
        width: 20px;
        height: 20px;
    }
</style>