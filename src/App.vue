<template>
  <div id="app">
    <div class="layer">
      <Form />
    </div>
    
  </div>
</template>

<script>
import Form from './views/Form.vue'

export default {
  components: {
    Form
  }
}
</script>


<style lang="scss">
@import '~bootstrap/scss/bootstrap.scss';
body {
    background-image: url('./assets/code.jpg ');
    background-repeat: no-repeat;
    background-size: cover;
}
.layer{
  position: relative;
	top: 0;
	left: 0;
	width: 100%;
	min-height: 200%;
	max-height: 50%;
	background: rgba(0,0,0,0.7);
}
</style>

