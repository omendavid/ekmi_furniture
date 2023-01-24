<template lang="">
    <header>
        <nav>
            <ul class="n-el-cont" v-if="screenSize > 375">
                <li class="h-u-l catalogue">Каталог
                    <ul class="catalogue-dropdown">
                        <li>Диваны </li>
                        <li>Кресла </li>
                        <li>Стулья </li>
                        <li>Кровати  </li>
                        <li>Матрацы </li>
                        <li>Пуфы </li>
                        <li>Эксклюзивная мебель</li>
                        <li>2D-3D модели</li>
                    </ul>
                </li>
                <li class="h-u-l individual">Индивидуальная мебель</li>
                <li class="h-u-l contacts">Контакты</li>
                <li class="h-u-l logo"><router-link to="/"><img src="../assets/img/logo.png" alt=""></router-link></li>
                <li class="h-u-l about"><router-link to="about"> О компании</router-link></li>
                <li class="h-u-l tel"><a href="tel:+38 (099)-638-45-37"> +38 (099)-638-45-37</a></li>
                <li class="h-u-l lang" @click="openLang">
                    {{ select.currentLang }} <i class="fa-solid fa-angle-down" :class="select.flip"></i>
                    <ul v-if="select.open == true" >
                        
                        <li v-for="lang in langs" :value="lang.lang" @click="select.currentLang = lang.lang">{{ lang.lang }}</li>

                    </ul>
                    
                    
                    <!-- <select id="">
                        <option 
                            v-for="lang in langs" 
                            :value="lang.lang"
                        >{{ lang.lang }}</option>
                    </select> -->
                </li>
            </ul>
            <ul class="n-el-cont-mini" v-else>
                <li class="h-u-l logo"><router-link to="/"><img src="../assets/img/logo_mini.png" alt=""></router-link></li>
                <li class="h-u-l-cont-side">
                    <li class="h-u-l lang" @click="openLang">
                        {{ select.currentLang }} <i class="fa-solid fa-angle-down" :class="select.flip"></i>
                        <ul v-if="select.open == true" >
                            <li v-for="lang in langs" :value="lang.lang" @click="select.currentLang = lang.lang">{{ lang.lang }}</li>
                        </ul>
                    </li>
                    <li class="h-u-l tel"><a href="tel:+38 (099)-638-45-37"><i class="fa-solid fa-phone"></i></a></li>
                    <li class="menu-cont" >
                        <ul class="burger-cont" @click="openMenu">
                            <span class="burger" :class="menu.active"></span>
                        </ul>
                        
                        <ul class="menu" :class="menu.openMen">
                            <li class="h-u-l catalogue" :class="catalogue.catOpened" ><span @click="openCat">Каталог</span>
                                <transition>
                                    <ul class="catalogue-drop" v-if="catalogue.catOpen == true">
                                        <li>Диваны </li>
                                        <li>Кресла </li>
                                        <li>Стулья </li>
                                        <li>Кровати  </li>
                                        <li>Матрацы </li>
                                        <li>Пуфы </li>
                                        <li>Эксклюзивная мебель</li>
                                        <li>2D-3D модели</li>
                                    </ul>
                                </transition>
                                
                            </li>
                            <li class="h-u-l individual">Индивидуальная мебель</li>
                            <li class="h-u-l contacts">Контакты</li>
                            <li class="h-u-l about"><router-link to="about"> О компании</router-link></li>
                            <li class="h-u-l">2D-3D модели</li>
                            <li class="h-u-l">Шоу-рум</li>
                            <li class="h-u-l">Страница партнёров дизайнеров</li>
                            <li class="h-u-l">Дилерам</li>
                            <li class="h-u-l">Контакты</li>
                        </ul>
                    </li>
                </li>
            </ul>   
        </nav>
    </header>
</template>
<script>
export default {
    name: 'Header',

    data() {
        return {
            
            select: {
                open: false,
                flip: '',
                currentLang: 'RU',
            },
            catalogue: {
                catOpen: false,
                catOpened: ''
            },
            menu: {
                opened: false,
                openMen: '',
                active: '',
            },
            langs: [
                {
                    lang: 'RU'
                },
                {
                    lang: 'UA'
                },
                {
                    lang: 'EN'
                },
            ]
        }
    },
    props: {
        screenSize: {
            type: Number
        }
    },
    methods: {
        openLang() {
            this.select.open = !this.select.open
            if(this.select.open == true){
                this.select.flip = 'flip'
            }else{
                this.select.flip = ''
            }
        },
        openMenu() {
            this.menu.opened = !this.menu.opened
            if(this.menu.opened == true){
                this.menu.openMen = 'opened'
                this.menu.active = 'active'
            }else {
                this.menu.openMen = ''
                this.menu.active = ''
            }
        },
        openCat() {
            this.catalogue.catOpen = !this.catalogue.catOpen
            if(this.catalogue.catOpen == true){
                this.catalogue.catOpened = 'catOpened'
            }
            else{
                this.catalogue.catOpened = ''
            }
        }

    },
   
    
}
</script>
<style lang="scss" scoped>


    .n-el-cont-mini{
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        flex-wrap: nowrap;
        max-width: 90.4%;
        width: 100%;
        margin: 0 auto;
        padding: 4vw 0px;

        list-style-type: none;
        font-weight: 600;
        line-height: 150%;

        .logo img{
            width:24.5vw
        }
        .h-u-l-cont-side{
            flex-basis: 45%;
            display: flex;
            flex-direction: row;
            justify-content: space-between;
            align-items: center;
            
            .h-u-l{
                font-size: 3.4vw;
                transition: all 0.3s ease;
                &.tel:hover , &.tel:focus{
                    color: #ff9619;
                }
            }
            .menu-cont{
                width: 6.6vw;
                padding: 2.6vw 0px;
                .burger-cont > span{
                    display: block;
                    height: 0.53vw;
                    width: 6.6vw;
                    background: black;
                    position: relative;
                    transition: all 0.4s cubic-bezier(0.29, 0.34, 0.14, 1.01);
                    z-index: 10;
                    &::before{
                        position: absolute;
                        display: block;
                        transform: translateY(-2.6vw);
                        content: '';
                        height: 0.53vw;
                        width: 6.6vw;
                        background: black;
                        transition: all 0.4s cubic-bezier(0.29, 0.34, 0.14, 1.01);
                    }
                    &::after{
                        position: absolute;
                        display: block;
                        transform: translateY(2.6vw);
                        content: '';
                        height: 0.53vw;
                        width: 6.6vw;
                        background: black;
                        transition: all 0.4s cubic-bezier(0.29, 0.34, 0.14, 1.01);
                    }

                    &.active {
                        background: transparent;
                        transform: translateX(-50px);
                        
                        
                        &::before{
                            transform: rotate(45deg) translate(34px, -34px);
                            top: 0;
                            height: 1px;
                            width: 4.5vw;
                        }
                        &::after{
                            transform: rotate(-45deg) translate(34px, 34px);
                            top: 0;
                            height: 1px;
                            width: 4.5vw;
                        }
                    }
                }
                .menu{
                    display: flex;
                    flex-direction: column;
                    justify-content: center;
                    background-color: rgb(255, 255, 255);
                    z-index: 9;
                    position: fixed;
                    width: 63.7vw;
                    height: 100%;
                    top: 0;
                    left: 0;
                    transform: translateX(157%);
                    transition: all 0.5s cubic-bezier(0, 0, 0.08, 1);

                    padding: 7.46vw 5.3vw;
                    box-sizing: border-box;
                    li{
                        color: #4B4844;
                        text-transform: capitalize;
                        list-style-type: none;
                        .catalogue-drop{
                            height: 0%;
                        }
                        
                    }
                     > li{
                        padding: 3.06vw 0px;
                     }
                    .catOpened{
                        span{
                            color: #ff9619;
                        }
                    }
                }
                .opened{
                    transform: translateX(67.3%);
                }
            }
        }
    }

.v-enter-active,
.v-leave-active {
    height: 100%;
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
    height: 0%;
  opacity: 0;
}


    .catalogue {
        position: relative;
    }

    .catalogue:hover {
        .catalogue-dropdown{
            display: block;
            opacity: 100%;
        }
    }
    .catalogue-dropdown {
        display: none;
        opacity: 0%;
        z-index: 1;
        position: absolute;
        background-color: #fff;
        list-style-type: none;
        box-shadow: 0px 0px 9px rgba(0, 0, 0, 0.15);
        min-width: 14.4vw;
        width: 100%;
        transition: all 0.3s ease;
        li{
            height: fit-content;
            line-height: initial;
        }
    }

    

    .catalogue-dropdown li{
        box-sizing: border-box;
        padding: 0.7vw;
        width: 100%;
        transition: all 0.2s ease;
        cursor: pointer;
    }
    
    .catalogue-dropdown li:hover{
        color: #ffffff;
        background-color: #ff9619;
    }

    .h-u-l{
       color :#343434;
       line-height: 150%;
    }

    .n-el-cont {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        flex-wrap: nowrap;
        max-width: 83.5%;
        width: 100%;
        margin: 0 auto;
        padding: 1.64% 0px;

        list-style-type: none;
        font-size: 13px;
        font-weight: 600;
        line-height: 20px;
       
    }

    .n-el-cont > li{
        cursor: pointer;
    }

    .logo img{
        width: 15vw;
    }

    .tel a{
        font-family: 'Open Sans';
        font-style: normal;
        font-weight: 600;
    }

    // .n-el-cont select {
    //     border: none;
    //     width: 100%;
    // }

    // .n-el-cont select option {
    //     border: none;
        
    //     background-color: white;
        
    // }

    .lang{
        position: relative;
        i{
            transition: all 0.3s ease;
        }
        ul{
            position: absolute;
            list-style-type: none;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            align-items: center;
            opacity: 100%;
            z-index: 1;
            position: absolute;
            background-color: #fff;
            list-style-type: none;
            box-shadow: 0px 4px 9px 2px rgba(0, 0, 0, 0.15);
            padding: 0px 6px;
            min-width: 1.4vw;
            width: min-content;
            transition: all 0.3s ease;
            li{
                display: inline-block;
                height: fit-content;
                line-height: 150%;
                transition: all 0.2s ease;
                &:hover{
                    color: #ff9619;

                }
            }
        }
    }

    .flip{
        transform: rotateX(180deg);
    }
    
   .n-el-cont select option:focus{
        background-color: white;
        color: #ff9619
    }

    .n-el-cont select option:hover {
        background-color: white;
        color: #ff9619
    }
    

    @media screen and (min-width: 1400px) {
        .n-el-cont{
            max-width: 1170px;
            padding: 25px 0px;
        }

        .logo img{
            width: initial;
        }

        .catalogue-dropdown{
            min-width: 208px;
            li{
                padding: 11px;
            }
        }
    }

    @media screen and (max-width: 890px) {
        .h-u-l{
            font-size: 1.4vw;
            select{
                font-size: 1.4vw;
            }
        }
    }

    @media screen and (max-width: 750px) {
        .lang {
            
            ul {
                
                padding: 0.4vw;
                
            }
        }
    }

    
</style>