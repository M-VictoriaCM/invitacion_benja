<script>
import imagen1 from '@/assets/img/coco.png'
import imagen2 from '@/assets/img/title2.png';
import imagen3 from '@/assets/img/coco_y_chorizo.png';
import Timer from '@/components/Timer/Timer.vue';
import Boton from '@/components/Boton.vue';
import PopupLocalizacion from '@/components/PopupLocalizacion.vue';
import logo from '@/assets/img/logo.png';
import SectionFooterVue from '@/components/SectionFooter.vue';
export default {
    name: 'invitacion',
    components: {
        Timer,
        Boton,
        PopupLocalizacion,
        SectionFooterVue
    },
    data() {
        return {
            imagen1,
            imagen2,
            imagen3,
            descripcion: '¡CUMPLO 3 AÑOS Y TE INVITÓ A FESTEJAR CONMIGO!',
            title: 'FIESTA',
            popup: false,
            logo
        }
    },
    methods: {
        togglePopUp() {
            this.popup = !this.popup
        }
    }
}
</script>
<template>
    <div class="invitacion__container content">
        <div class="invitacion__img1">
            <img :src="imagen1" class="img_1" alt="imagen">
        </div>
        <div class="invitacion_title">
            <img :src="imagen2" class="img_2" alt="imagen">
        </div>
        <span class="content_text">
            <p class="text1">{{ descripcion }}</p>
        </span>
        <Timer />
        <div class="invitacion__img2">
            <img :src="imagen3" class="img_3" alt="imagen">
            <h1 class="title">{{ title }}</h1>
        </div>
        <div class="descripcion_fiesta">
            <p class="evento">Te espero el sábado <strong>07 de septiembre</strong> a las <strong>19 hs</strong>. en el
                salón de Pita.</p>
        </div>
        <div class="container__button">
            <PopupLocalizacion v-show="popup" @close="togglePopUp()" />
            <Boton label="ENCENDER GPS" customClass="btn-mayor" @click="togglePopUp()" />
        </div>
        <div class="box__footer">
            <SectionFooterVue/>
        </div>


        <!-- <div class="box__footer">
            <div class="mensaje_comercial">
                <img :src="logo" alt="logo">
                
            </div>
            <div class="footer">
                <div class="container__footer">
                    <div class="text_desarrolladores">
                        <p class="dev1">Develop by</p>
                        <p class="dev2">Teinvite.io</p>
                        <a href="https://www.instagram.com/teinviteok/" target="_blank" rel="noopener noreferrer">
                            <i class="fa-brands fa-instagram icon"></i>
                        </a>
                    </div>
                </div>
            </div>
        </div> -->
    </div>
</template>
<style>
.invitacion__container {
    width: 100%;
    height: 100vh;
    background-image: url('../assets/img/fondoTexturado.png');
    background-repeat: no-repeat;
    background-size: cover;
    overflow: scroll;
}

.content {
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center;
}

.invitacion__img1 {
    width: 203px;
    height: auto;
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 1rem;

}

.img_1 {
    width: 100%;
    height: auto;
}

.invitacion_title {
    width: 286px;
    height: auto;
    display: flex;
    justify-content: center;
    align-items: center;
}

.img_2 {
    width: 100%;
    height: auto;
}

.content_text {
    width: 70%;
    height: auto;
    margin-top: 1rem;
}

.text1 {
    color: var(--color-font);
    font-family: Rockwell-Bold;
    font-size: 20px;
    font-weight: normal;
    line-height: 100%;
    text-align: center;
}

.invitacion__img2 {
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
    position: relative;
}

.img_3 {
    width: 200px;
    height: auto;
    position: relative;
    z-index: 1;
}

.title {
    font-family: Rockwell-Bold;
    font-weight: normal;
    font-size: 2.5rem;
    color: var(--color-counter2);
    line-height: 100%;
    text-align: center;
    position: absolute;
    bottom: 0;
    z-index: 0;
}

.descripcion_fiesta {
    width: 70%;
    height: auto;
    display: flex;
    justify-content: center;
}

.container__button {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-bottom: .5rem;
}

.evento {
    font-family: Montserrat;
    font-weight: normal;
    font-size: 14px;
    color: black;
    text-align: center;
    line-height: 100%;
}

.box__footer {
    margin-top:1rem;
    width: 100%;
    height: 100%;
}


</style>
