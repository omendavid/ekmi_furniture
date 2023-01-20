<template lang="">
    <section class="sec-1">
        <div class="sec-1-cont">
            <div class="sec-1-flex" >
                <div class="s-1-p1">
                    <h2><span>Л</span>УЧШАЯ ЖИЗНЬ, СОЗДАННАЯ ДЛЯ ВАС!</h2>
                    <button>перейти в КАталог</button>
                </div> 
                <div class="s-1-p2">
                    <div class="since-div">
                        <p>Основано в 1993 году</p>
                    </div>
                    <agile  :autoplay="true" :autoplaySpeed="3000" :pauseOnDotsHover="true" :navButtons="false" :fade="true" >
                        <div class="slide">
                            <img src="../assets/img/couch_1.png" alt="">
                        </div>
                        <div class="slide">
                            <img src="../assets/img/couch_2.png" alt=""> 
                        </div>
                        <div class="slide">
                            <img src="../assets/img/couch_3.png" alt=""> 
                        </div>
                    </agile>
                </div>
            </div>
        </div>
    </section>
</template>
<script>
/* ----------------------------- import for slider ----------------------------- */

import {VueAgile} from 'vue-agile';




/* ----------------------------- ----------------------------- ----------------------------- */

export default {
    name: 'UpperSlider',
    data() {
        return {
            sliders: [
                {
                    img: '../assets/img/couch_1.png'
                },
                // {
                //     img: '../assets/img/couch_2.png'
                // },
                // {
                //     img: '../assets/img/couch_3.png'
                // },
            ]
        }
    },
    components: {
        agile: VueAgile
    }
}
</script>
<style lang="scss" >



.sec-1 {
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

.sec-1-cont{
    display: flex;
}
.sec-1-flex{
    width: 83.5%;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    margin: 0 auto;



}

.s-1-p1{
    display: flex;
    flex-direction: column;
    gap: 60px;
    h2{
        font-weight: 600;
        font-size: 42px;
        color: white;
        text-transform: capitalize;
        max-width: 270px;
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

.s-1-p2{
    width: 100%;
    max-width: 70%;

    .since-div{
        p{
            font-weight: 400;
            font-size: 20px;
            color: white;
            line-height: 127.5%;
            padding: 35px 0px;
            text-align: end;
        }
    }

}

.agile {

    .agile__actions{
        margin: 2.5% 0px 0px 0px;
        .agile__dots{
            gap: 10px;
            .agile__dot{
                border: none;
                border-radius: 50%;
                background-color: #f2f3f5;

                &--current {
                    background-color: #ff9619;
                    border-radius: 50%;
                }

                button{
                    padding: 7px;
                    background-color: transparent;
                    border: none;
                    border-radius: 50%;
                    
                }
            }

        } 
    
    }
		

        
        
    }


// Slides styles
.slide{
	display: block;
	width: 100%;
}


@media screen and ( min-width: 1440px) {
    .sec-1-flex{
        max-width: 1170px;
    }
}


    
</style>