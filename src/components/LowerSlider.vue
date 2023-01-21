<template lang="">
    <section class="sec-2">
        <div class="sec-2-cont">
            <div class="s-2-flex">
                <div class="s-2-f-h-cont">
                    <h2><span>Н</span>овинки</h2>
                </div>
                <div class="s-2-slider-cont">
                    <div class="slide">
                        <div class="s-2-s-img-cont">
                            <img src="../assets/img/section_2/couch_1.png" alt="">
                        </div>
                        <div class="s-2-s-info-cont">
                            <h3>Martin</h3>
                            <p>15 000 UAH</p>
                        </div>
                    </div>
                </div>
                <div class="s-2-f-but"><button>перейти в КАталог</button></div>
            </div>
        </div>
    </section>
</template>
<script>
export default {
    
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
    max-width: 270px;
    height: 348px;
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
        max-width: 18.75vw;
        height: 24.1vw;
        

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
    

    
</style>