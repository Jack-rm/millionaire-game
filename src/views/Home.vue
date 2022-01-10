<template>
  <div class="home">
    <header>
      <img alt="Vue logo" src="../assets/logo-millionaire.png" />
    </header>
    <Container />
  </div>
</template>

<script>
// @ is an alias to /src
import Container from "@/components/Container.vue";

export default {
  name: "Home",
  components: {
    Container,
  },
  data: function(){
    return{
    }
  }
};
</script>
<style scoped lang="scss">
header {
  height: 350px;
  padding-top: 50px;
  padding-bottom: 50px;

  img {
    height: 100%;
  }
}
</style>
