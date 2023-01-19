<template lang="">
    <div class="sec-1">
        <div class="slider-cont">
            <div
                class="slider" 
                v-for="slider in sliders"
            >
                <div class="s-1-slider-p1">
                    <h2><span>Л</span>УЧШАЯ ЖИЗНЬ, СОЗДАННАЯ ДЛЯ ВАС!</h2>
                    <button>перейти в КАталог</button>
                </div>
                <div class="s-1-slider-p2"><img :src="slider.img" alt=""></div>
            </div>
        </div>
    </div>
</template>
<script>
/* ----------------------------- default javascript for slider ----------------------------- */





/* ----------------------------- ----------------------------- ----------------------------- */

export default {
    name: 'UpperSlider',
    data() {
        return {
            sliders: [
                {
                    img: '../assets/img/couch_1.png'
                },
                {
                    img: '../assets/img/couch_2.png'
                },
                {
                    img: '../assets/img/couch_3.png'
                },
            ]
        }
    }
}
</script>
<style lang="scss" scoped>

.sec-1 {
    overflow: hidden;
    height: 100%;
    max-height: 744px;
    height: 744px;
    position: relative;
}

.sec-1::before {
    z-index: -1;
    content: '';
    position: absolute;
    width: 100%;
    height: 79%;
    left: 0px;
    top: 0px;

    background: #CCB2A3;
}

.slider-cont{
    display: flex;
}
.slider{
    width: 100%;
}

.s-1-slider-p1{
    h2{
        color: white;
        span{
            color: #ff9619;
        }
    }
    button{
        background: #ff9619;
        color: white;
        text-transform: uppercase;
        border: none;
        font-weight: 700;
        font-size: 16px;   
        padding: 13px 21px;
    }
}
    
</style>