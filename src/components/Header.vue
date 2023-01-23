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
                    {{ currentLang }} <i class="fa-solid fa-angle-down" :class="flip"></i>
                    <ul v-if="open == true" >
                        
                        <li v-for="lang in langs" :value="lang.lang" @click="currentLang = lang.lang">{{ lang.lang }}</li>

                    </ul>
                    
                    
                    <!-- <select id="">
                        <option 
                            v-for="lang in langs" 
                            :value="lang.lang"
                        >{{ lang.lang }}</option>
                    </select> -->
                </li>
            </ul>
            <ul class="n-el-cont-mini" v-if="screenSize <= 375">
                <li class="h-u-l logo"><router-link to="/"><img src="../assets/img/logo_mini.png" alt=""></router-link></li>
                <li class="h-u-l-cont-side">
                    <li class="h-u-l lang" @click="openLang">
                        {{ currentLang }} <i class="fa-solid fa-angle-down" :class="flip"></i>
                        <ul v-if="open == true" >
                            <li v-for="lang in langs" :value="lang.lang" @click="currentLang = lang.lang">{{ lang.lang }}</li>
                        </ul>
                    </li>
                    <li class="h-u-l tel"><a href="tel:+38 (099)-638-45-37"><i class="fa-solid fa-phone"></i></a></li>
                    <li class="burg-cont" @click="openMenu"><span class="burger" :class="active"></span></li>
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
            screenSize : 1440,
            open: false,
            flip: '',
            currentLang: 'RU',
            openMen: false,
            active: '',
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
            this.open = !this.open
            if(this.open == true){
                this.flip = 'flip'
            }else{
                this.flip = ''
            }
        },
        openMenu() {
            this.openMen = !this.openMen
            if(this.openMen == true){
                this.active = 'active'
            }else {
                this.active = ''
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
        .h-u-l-cont-side{
            flex-basis: 45%;
            display: flex;
            flex-direction: row;
            justify-content: space-between;
            align-items: center;
            
            .h-u-l{
                font-size: 3.4vw;
            }
            .burg-cont{
                width: 25px;
                span{
                    display: block;
                    height: 2px;
                    width: 25px;
                    background: black;
                    position: relative;
                    transition: all 0.3s ease;
                    &::before{
                        position: absolute;
                        display: block;
                        top: -10px;
                        content: '';
                        height: 2px;
                        width: 25px;
                        background: black;
                        transition: all 0.3s ease;
                    }
                    &::after{
                        position: absolute;
                        display: block;
                        top: 10px;
                        content: '';
                        height: 2px;
                        width: 25px;
                        background: black;
                        transition: all 0.3s ease;
                    }

                    &.active {
                        background: white;
                        height: 0px;
                        &::before{
                            transform: rotateZ(45deg);
                            top: 0;
                        }
                        &::after{
                            transform: rotateZ(-45deg);
                            top: 0;
                        }
                    }
                }
            }
        }
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

    @media screen and ( max-width: 600px ) {
        
    }
</style>