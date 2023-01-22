<template>
  <div class="sections-cont">
    <UpperSlider />
    <LowerSlider />
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
}
}
</script>
