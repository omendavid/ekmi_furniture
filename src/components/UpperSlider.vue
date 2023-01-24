<template lang="">
    <section class="sec-1">
        <div class="sec-1-cont" v-if="screenSize > 375 ">
            <div class="sec-1-flex" >
                <div class="s-1-p1">
                    <h2><span>Л</span>УЧШАЯ ЖИЗНЬ, СОЗДАННАЯ ДЛЯ ВАС!</h2>
                    <router-link to=""><button>перейти в КАталог</button></router-link>
                </div> 
                <div class="s-1-p2">
                    <div class="since-div">
                        <p>Основано в 1993 году</p>
                    </div>
                    <agile  :autoplay="true" :autoplaySpeed="3000" :pauseOnDotsHover="true" :navButtons="false" :fade="true" >
                        <div class="slide"
                        v-for="slider in sliders">
                            <img :src="slider.img" alt=""> 
                        </div>
                    </agile>
                </div>
            </div>
        </div>

<!-- ---------------------------------- mobile ---------------------------- -->


        <div class="sec-1-cont-mobile" v-else>
            <div class="sec-1-flex-mobile">
                <div class="s-1-p1">
                    <h2><span>Л</span>УЧШАЯ ЖИЗНЬ, СОЗДАННАЯ ДЛЯ ВАС!</h2>
                </div> 
                <div class="s-1-p2">
                    <agile  :autoplay="true" :autoplaySpeed="3000" :pauseOnDotsHover="true" :navButtons="false" :fade="true" >
                        <div class="slide"
                        v-for="slider in sliders">
                            <img :src="slider.img" alt=""> 
                        </div>
                    </agile>
                </div>
                <div class="since-div">
                    <p>Основано в 1993 году</p>
                </div>
                <div class="but-div">
                    <router-link to=""><button>перейти в КАталог</button></router-link>
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
                    img: require('../assets/img/section_1/couch_1.png')
                },
                {
                    img: require('../assets/img/section_1/couch_2.png')
                },
                {
                    img: require('../assets/img/section_1/couch_3.png')
                },
            ]
        }
    },
    components: {
        agile: VueAgile
    },
    props: {
        screenSize: {
            type: Number
        }
    }
}
</script>
<style lang="scss" scoped>


.sec-1-cont-mobile{
    padding: 8vw 0 15.2vw 0;
    .sec-1-flex-mobile{
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        flex-wrap: nowrap;
        gap: 5.33vw;
    }
    .s-1-p1{
        width: 100%;
        h2{
            line-height: 7.33vw;
            font-size: 6.66vw;
            width: 95%;
            padding-left: 4.8vw;
            
        }
    }

    

    .since-div{
        text-align: center;
        p{
            font-size: 5.33vw;
            color: white;
            
        }
    }
    .but-div{
        text-align: center;
        button{
        background: #ff9619;
        color: white;
        text-transform: uppercase;
        border: none;
        font-weight: 700;
        font-size: 4.27vw;   
        padding: 3.7vw 5.6vw;
        transition: all 0.3s ease;
        cursor: pointer;
        
        &:hover{
            background: #5B5B5B;
        }
    }
    }
}



.sec-1 {

    max-height: 51.6vw;
    height: 100%;
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
    margin: 0 auto;
    width: 83.5%;
}
.sec-1-flex{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    gap: 2vw;
    
}

.s-1-p1{
    display: flex;
    flex-direction: column;
    gap: 4.1vw;
    h2{
        font-weight: 600;
        font-size: 42px;
        color: white;
        text-transform: capitalize;
      
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
        padding: 0.9vw 1.4vw;
        transition: all 0.3s ease;
        cursor: pointer;
        &:hover{
            background: #5B5B5B;
        }
    }
}

.s-1-p2{
    width: 100%;
    max-width: 70%;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    gap: 2vw;
    padding-top: 2vw;
    .since-div{
        p{
            font-weight: 400;
            font-size: 20px;
            color: white;
            line-height: 127.5%;
            
            text-align: end;
        }
    }

}
    // .agile {

    //     .agile__actions{
    //         margin: 2.5% 0px 0px 0px;
    //         .agile__dots{
    //             gap: 10px;
    //             .agile__dot{
    //                 border: none;
    //                 border-radius: 50%;
    //                 background-color: #f2f3f5;

    //                 &--current {
    //                     background-color: #ff9619;
    //                     border-radius: 50%;
    //                 }

    //                 button{
    //                     padding: 0.4vw;
    //                     background-color: transparent;
    //                     border: none;
    //                     border-radius: 50%;

    //                 }
    //             }

    //         } 
        
    //     }

    //     &__slide{
    //         display: flex;
    //         img{
    //             width: 60vw;
    //             object-fit: cover;
    //             object-position: center;
    //         }
    //     }
    
    // }



// Slides styles
.slide{
	display: block;
	width: 100%;
}


@media screen and ( min-width: 1400px) {

    .sec1 {
        max-height: 744px;
    }

    .sec-1-cont{
        max-width: 1170px;
    }

    .sec-1-flex{
        gap: 30px;
    }

    .s-1-p1{
        gap: 60px;
        button {
            padding: 13px 21px;
        }
    }

    .s-1-p2{
        padding-top: 35px;
        max-width: 70%;
        gap: 35px;
    }

    // .agile{
    //     .agile__actions{
    //         .agile__dots{
    //             .agile__dot{
    //                 button{
    //                     padding: 7px;
    //                 }
    //             }
    //         }
    //     }

    //     &__slide{
    //         img {
    //             width: initial;
    //         }
    //     }
    // }
}

@media screen and ( max-width: 1270px ) {
    .s-1-p1{
        h2{
            font-size: 3.3vw;
        }
        button{
            font-size: 1.3vw;
        }
    }
    .s-1-p2 {
        .since-div{
            p{
                font-size: 1.6vw;
            }
        } 
    }

    // .agile, .agile__track{
    //     height: 40vw;
    // }
}

@media screen and ( max-width: 376px ) {
    .sec-1{
        max-height: none;
        &::before{
            height: 100%;
        }
    }
}


    
</style>

<style lang="scss" >

.sec-1{
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
                        padding: 0.4vw;
                        background-color: transparent;
                        border: none;
                        border-radius: 50%;
                    
                    }
                }
            
            } 
        
        }

        &__slide{
            display: flex;
            img{
                width: 60vw;
                object-fit: cover;
                object-position: center;
            }
        }

    }
}

@media screen and ( min-width: 1400px ){

    .sec-1{
        .agile{
            .agile__actions{
                .agile__dots{
                    .agile__dot{
                        button{
                            padding: 7px;
                        }
                    }
                }
            }

            &__slide{
                img {
                    width: initial;
                }
            }
        }
    }
}


@media screen and ( max-width: 1270px ) {
    
    .sec-1{
        .agile, .agile__track{
        height: 40vw;
        }
    }
    
}

@media screen and (max-width: 376px) {
    .sec-1 {
        .agile, .agile__track{
            width: 100vw;
            height: 100%;
            
        }

        .agile{
            &__slide{
                img {
                    width: 100vw;
                }
            }
            .agile__actions{
                .agile__dots{
                    .agile__dot{
                    
                    
                        button{
                            padding: 0.93vw;
                        }
                    }
                }
            }
        }
    }
}


</style>