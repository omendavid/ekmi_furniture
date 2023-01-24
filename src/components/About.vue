<template lang="">
    <section class="sec-1">
        <div class="s-1-cont">
            <div class="s-1-f">
                <div class="s-1-a">
                    <div class="s-1-a-info">
                        <h2><span>К</span>то покупает нашу мебель </h2>
                        <p>Фабрика «Экми-Мебель» — один из ведущих производителей мебели в Украине – открыта к поиску партнёров и предлагает взаимовыгодное сотрудничество. На данный момент дилерская сеть насчитывает более 30 салонов по всей Украине. </p>
                    </div>
                    <div class="s-1-a-img-c">
                        <img src="../assets/img/about/couch.png" alt="">
                    </div>
                </div>
                <div class="s-1-a">
                    <h2><span>Г</span>де создают нашу мебель</h2>
                    <div class="s-1-a-middle-cont">
                        <div class="s-1-a-img-c">
                            <img src="../assets/img/about/couch.png" alt="">
                        </div>
                        <div class="s-1-a-info">
                            <p>Дилер — это наш партнер и посредник между фабрикой и конечным потребителем. В рамках такого партнерства мы, со стороны фабрики, оказываем любую помощь в работе: предоставляем скидку на выставочные образцы при открытии салона, обеспечиваем всеми материалами с которыми работает фабрика. Предоставляем полностью рабочее программное обеспечение для расчета стоимости мебели и прорисовки модели в 3D.</p>
                        </div> 
                    </div>
                                     
                </div>
                <div class="s-1-a">
                    <div class="s-1-a-info">
                        <h2><span>Э</span>тапы сотрудничества</h2>
                        <p>У нас большая складская программа, большинство материалов и фурнитуры постоянно есть на складе.В таком случае, заказы изготавливаются за 13-15 дней.</p>
                    </div>
                    <div class="s-1-a-img-c">
                        <img src="../assets/img/about/couch.png" alt="">
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>
<script>
export default {
    name: "About",
    props: {
        screenSize: {
            type: Number
        }
    }
}
</script>
<style lang="scss" scoped>

    .s-1-cont{
        max-width: 1064px;
        margin: 0 auto;
    }


    .s-1-a{
        color: #343434;
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        &:nth-child(1){
            padding-top: 35px;
        }
        &:nth-child(2){
            padding: 140px 0px 130px 0px;
            display: flex;
            flex-direction: column;
            gap: 40px;
            .s-1-a-img-c{
                position: relative;
                img{
                    transform: rotateY(180deg);
                }
                    &::after{
                        position: absolute;
                        z-index: -1;
                        content: '';
                        width: 282px;
                        height: 333px;
                        bottom: -50px;
                        left: -70px;
                        background: #5B5B5B;;
                    }
            }
        }

        h2{
            font-weight: 500;
            font-size: 30px;
            letter-spacing:  0.8px;
            span{
                color: white;
                position: relative;
                &::before{
                    position: absolute;
                    z-index: -1;
                    content: '';
                    width: 58px;
                    height: 58px;
                    bottom: 50%;
                    right: -2px;
                    transform: translateY(50%);
                    background: #A9C2BE;
                }
            }
        }
        p{
            font-weight: 300;
            font-size: 18px;
            line-height: 150%;

        }
        
    }

    .s-1-a-middle-cont{
        display: flex;
        width: 94.2%;
        justify-content: space-between;
        margin: 0 auto;
    }

    .s-1-a-info{
        display: flex;
        flex-direction: column;
        gap: 46px;
        max-width: 530px;
    }

    .s-1-a-img-c{
        position: relative;
            &::after{
                position: absolute;
                z-index: -1;
                content: '';
                width: 282px;
                height: 333px;
                bottom: -50px;
                right: -70px;
                background: #A9C2BE;
            }
        }


        @media screen and (max-width: 1440px) {
            .s-1-cont{
                max-width: 73.8vw;
            }

            .s-1-a{
                h2{
                    font-size: 2.085vw;
                    span{
                        &::before{
                            width: 4vw;
                            height: 4vw;
                        }
                    }
                }
                p{
                    font-size: 1.25vw;
                }
                img{
                    width: 29.86vw;
                }

            
       
                &:nth-child(1){
                    padding-top: 2.43vw;
                }
                &:nth-child(2){
                    padding: 9.7vw 0px 9vw 0px;

                    gap: 2.7vw;
                    .s-1-a-img-c{
                            &::after{
                                width: 19.58vw;
                                height: 23.12vw;
                                bottom: -3.47vw;
                                left: -4.86vw;
                            }
                    }
            }
                
            }

            .s-1-a-info{
                gap: 3.19vw
            }

            .s-1-a-img-c{
            
                &::after{
                    
                    width: 19.58vw;
                    height: 23.12vw;
                    bottom: -3.47vw;
                    right: -4.86vw;
                }
            }
            
        }

        @media screen and ( max-width: 376px ) {
            .s-1-cont{
                max-width: 90.4%;
            }
            .s-1-a{
                flex-direction: column;
                &:nth-child(2){
                    display: flex;
                    flex-direction: column;
                    h2{
                        font-size: 5.33vw;
                        width: 76.2vw;
                        margin: 0 auto;
                    }
                    .s-1-a-middle-cont{
                        display: flex;
                        flex-direction: column-reverse;
                        width: 100%;
                        .s-1-a-img-c{
                            width: 100%;
                            img{
                                width: 100%;
                            }
                            &::after{
                                width: 57.86vw;
                                height: 67.73vw;
                            }
                        }
                    }
                }
                .s-1-a-img-c{
                    &::after{
                        width: 57.86vw;
                        height: 67.73vw;
                    }
                    img{
                        width: 100%;
                    }
                }

                .s-1-a-info{
                    max-width: 76.2vw;
                    margin: 0 auto;
                    h2{
                        font-size: 5.33vw;
                        
                    }
                    p{
                        font-size: 3.73vw;
                        line-height: 5.04vw;
                    }
                }
            }

            .s-1-a{
                h2{
                    span{
                        &::before{
                            right: -0.4vw;
                            width: 9.6vw;
                            height: 9.6vw;
                            }
                    }
                }
            }
        }  
        
        
    

    

</style>