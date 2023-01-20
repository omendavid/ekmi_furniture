<template lang="">
    <header>
        <nav>
            <ul class="n-el-cont">
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
                <li class="h-u-l lang">
                    <select name="" id="">
                        <option 
                            v-for="lang in langs"
                            :key="index"
                            :value="lang.lang"
                        >{{ lang.lang }}</option>
                    </select>
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
    }
}
</script>
<style lang="scss" scoped>

    nav {
        // padding: 1.64% 0;
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
        min-width: 208px;
        width: 100%;
        transition: all 0.3s ease;
    }

    

    .catalogue-dropdown li{
        box-sizing: border-box;
        padding: 11px 11px;
        width: 100%;
        transition: all 0.2s ease;
        cursor: pointer;
    }
    
    .catalogue-dropdown li:hover{
        color: #ffffff;
        background-color: #ff9619;
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

    .n-el-cont select {
        border: none
    }

    .n-el-cont select option {
        border: none;
        box-shadow: 0px 4px 9px rgba(0, 0, 0, 0.15);
        background-color: white;
        color: #ff9619;
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
    }

    @media screen and (max-width: 890px) {
        .h-u-l{
            font-size: 1.4vw;
        }
    }
</style>