<template lang="">
    <section class="sec-2">
        <div class="sec-2-cont">
            <div class="s-2-flex">
                <div class="s-2-f-h-cont">
                    <h2><span>Н</span>овинки</h2>
                </div>
                <div class="s-2-slider-cont">
                    <div class="s-2-s-but-cont"><img @click="$refs.carousel.goToPrev()" src="../assets/img/section_2/arrow.png" alt=""></div>
                    <agile ref="carousel" :autoplay="true" :pauseOnHover="true" :centerMode="true" :dots="false" :navButtons="false" :slidesToShow="3">
                        <div class="slide" v-for="slider in sliders">
                            <div class="s-2-s-img-cont">
                                <img :src="slider.img" alt="sec_img">
                            </div>
                            <div class="s-2-s-info-cont">
                                <h3>{{ slider.name }}</h3>
                                <p>{{ slider.price }} UAH</p>
                            </div>
                        </div>
                    </agile>
                    <div class="s-2-s-but-cont"><img src="../assets/img/section_2/arrow.png" @click="$refs.carousel.goToNext()" alt=""></div>
                </div>
                <div class="s-2-f-but"><button>перейти в КАталог</button></div>
            </div>
        </div>
    </section>
</template>
<script>
import {VueAgile} from 'vue-agile';

export default {
    name: 'LowerSlider',
    data() {
        return {
            sliders: [
                {
                    img: require('../assets/img/section_2/couch_2.png'),
                    name: 'MARTIN',
                    price: '15 000'
                },
                {
                    img: require('../assets/img/section_2/couch_1.png'),
                    name: 'Alba',
                    price: '15 000'
                },
                {
                    img: require('../assets/img/section_2/couch_3.png'),
                    name: 'Laura',
                    price: '15 000'
                },

            ]
        }
    },
    components: {
        agile: VueAgile
    }
    
}
</script>
<style lang="scss" scoped>


.sec-2{
    padding: 9.3vw 0px 13.5vw 0px;
}

.sec-2-cont{
    margin: 0 auto;
    width: 83.5%;
}

.s-2-flex{
    .s-2-f-h-cont{
        h2{
            color: #343434;
            font-weight: 700;
            font-size: 35px;
            span{
                color: #FF9619;
            }
        }
    }
    .s-2-slider-cont{
        padding: 80px 60px;
        display: flex;
        align-items: center;
        > div:nth-child(1){
            transform: rotateY(180deg);
        }
        .s-2-s-but-cont{
            cursor: pointer;
        }

    }

    .s-2-f-but{
        text-align: center;
        button{
            background: #ff9619;
            color: white;
            text-transform: uppercase;
            border: none;
            font-weight: 700;
            font-size: 16px;
            padding: 14px 21px;   
            transition: all 0.3s ease;
            cursor: pointer;
            &:hover{
                background: #5B5B5B;
            }
        }
    }
}

.slide{
    width: 270px;
    height: 348px;
    padding: 0px 41.5px;
    box-sizing: border-box;
    .s-2-s-img-cont{
        display: flex;
        background: #F2F3F5;
        height: 79.8%;
        
         img{
            margin: auto auto;
        }
    }

    .s-2-s-info-cont{
        text-transform: uppercase;
        text-align: center;
        display: flex;
        flex-direction: column;
        gap: 5px;
        padding-top: 15px;
        h3{
            font-weight: 500;
            font-size: 18px;
        }
        p{
            font-family: 'Open Sans', sans-serif;
            font-weight: 600;
            font-size: 18px;
            color: #FF9619;
        }
    }
}  

@media screen and ( min-width: 1400px ) {
    .sec-2{
        padding: 135px 0px 195px 0px;
    }
    .sec-2-cont{
        max-width: 1170px;
    }
    
}

@media screen and ( max-width: 1270px ) {
    .s-2-flex{
        .s-2-f-h-cont{
            h2{
                font-size: 2.75vw;
            }
        }
        .s-2-f-but{
            button{
                font-size: 1.3vw;
                padding: 0.9vw 1.4vw;
            }
        }
    }
    .slide{
        width: 18.75vw;
        height: 24.1vw;
        padding: 0px 2.8vw;
        

        .s-2-s-img-cont{
            img{
                width: 100%;
                object-fit: cover;
                object-position: center;
            }
        }
        .s-2-s-info-cont{
            gap: 0.3vw;
            padding-top: 1vw;
            h3{
                font-size: 1.45vw;
            }
            p{
                font-size: 1.45vw;
            }
        }    
    }
    .s-2-flex{
        .s-2-slider-cont{
            padding: 5.5vw 4.1vw;
        }
    }
    
}
@media screen and ( max-width: 1200px ) {
    .s-2-flex{
        .s-2-slider-cont{
            .s-2-s-but-cont img{
                width: 1.5vw;
            }
        }
    }
}

    
</style>

<style lang="scss" >

.sec-2{
    .agile{
        max-width: 1050px;
    }
    .agile__slides {
        
        justify-content: space-between;
    }
}

@media screen and ( max-width: 1440px ) {
    .sec-2{
        .agile{
            max-width: 72.9vw;
        }
    }
}



</style>