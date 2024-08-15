<template>
    <div class="container">
        <div>
            <img class="gradientBanner" :src="gradient" alt="">
        </div>
        <div class="containerInfo p-20">
            <div class="generalInfo">
                <div>
                    <img class="profilePicture" :src="profilePicture" alt="">
                </div>
                <div class="textGeneralInfo">
                    <div>
                        <h2>John Doe</h2>
                    </div>
                    <div class="internInfo">
                        <div>
                            <img class="iconBanner" :src="paletaIcon" alt="">
                            <span>Coder</span>
                        </div>
                        <div>
                            <img class="iconBanner" :src="ubicacionIcon" alt="">
                            <span>Medellín</span>
                        </div>
                        <div>
                            <img class="iconBanner" :src="calendarioIcon" alt="">
                            <span>Joined April 2021</span>
                        </div>
                    </div>
                </div>
            </div>
            <div class="containerButton p-16">
                <a class="p-15">
                    <img class="iconBanner" :src="usuarioActivoIcon" alt="">
                    <span>Connected</span>
                </a>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    .container {
        background-color: #fff;
        border-radius: 5px;
        display: flex;
        flex-direction: column;
        margin-top: 30px;
        box-shadow: 1px 1px 1px rgba(0, 0, 0, 0.1);

        .gradientBanner {
            width: 100%;
            height: 250px;
            border-radius: 5px 5px 0 0;
        }

        .containerInfo {
            display: flex;
            justify-content: space-between;

            .profilePicture {
                width: 150px;
                height: 150px;
                border-radius: 10px;
                margin-top: -50px;
                border: 5px solid #fff;
            }

            .generalInfo {
                display: flex;
                align-items: center;

                .textGeneralInfo {
                    margin-left: 10px;
                    
                    h2 {
                        margin-bottom: 20px;
                    }
                    
                    .internInfo {
                        display: flex;

                        div {
                            display: flex;
                            margin-right: 20px;

                            span {
                                color: #939393;
                            }
                        }
                    }
                }
            }
        }
    
        .iconBanner {
            width: 20px;
            height: 20px;
            margin-right: 10px;
        }

        .containerButton {
            margin-top: auto;

            a {
                background-color: #7367ef;
                box-shadow: #7267ef6a 2px 2px 2px 2px;
                color: #fff;
                border-radius: 8px;
                font-weight: bold;
                display: flex;
                align-items: center;
                justify-content: center;
                width: 180px;
            }
        }
    }
</style>

<script setup lang="ts">
    import gradient from '@/assets/images/gradient.png'
    import profilePicture from '@/assets/images/profilePictures/profilePicture1.png'

    import paletaIcon from '@/assets/images/paleta.png'
    import ubicacionIcon from '@/assets/images/ubicacion.png'
    import calendarioIcon from '@/assets/images/calendario.png'
    import usuarioActivoIcon from '@/assets/images/usuarioActivo.png'
</script>