<template>
  <div class="sections-cont">
    <UpperSlider :screenSize="screenSize" />
    <LowerSlider :screenSize="screenSize" />
  </div>
</template>

<script>
// @ is an alias to /src
import LowerSlider from '@/components/LowerSlider';
import UpperSlider from '@/components/UpperSlider';


export default {
  name: 'Home',
  components: {
    UpperSlider,
    LowerSlider
},
  props: {
    screenSize: {
        type: Number
    }
}
}
</script>


<style lang="scss">

</style>