<template>
  <div class="main">
    <Header :screenSize="screenSize" />
    <router-view/>
  </div>
  
</template>

<script>
import Header from './components/Header';

export default {
  data() {
    return {
      screenSize: 1920
    }
  },
  components: {
  Header
},
mounted(){
        this.screenSize = window.screen.width

        window.onresize=()=>{
            this.screenSize = window.screen.width
        }
    }
}

</script>

<style lang="scss">

*{
  margin: 0;
  padding: 0;
}

body{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Raleway', sans-serif;
}

a {
  color: inherit;
  text-decoration: none;
}

::-webkit-scrollbar{
  width: 6px;
}

::-webkit-scrollbar-track{
  background: rgb(221, 221, 221);
}
::-webkit-scrollbar-thumb{
  background: #A9C2BE;
  border-radius: 6px;
}



</style>
