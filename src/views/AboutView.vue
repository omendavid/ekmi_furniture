<template>
  <div class="about">
    <About :screenSize="screenSize" />
  </div>
</template>

<script>
import About from '@/components/About';

export default {
  components: {
    About,
  },
  props: {
    screenSize: {
      type: Number
    }
  }
}
</script>
