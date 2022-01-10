<template>
        <div class="col-12">
          <h2 class="pb-3">Domanda n. {{currentQuestion + 1}} di {{quiz.length}}</h2>
          <h4>{{quiz[currentQuestion].questionText}}</h4>
        </div>
</template>

<script>
import quiz from "../data/quiz";
export default {
  name: "Questions",
  props: [
    'currentQuestion'
  ],
  data: function(){
    return{
        quiz,
    }
  }
};
</script>

<style scoped lang="scss">
@import "../style/general.scss";

  h1,
  h2,
  h3,
  h4,
  h5 {
    color: white;
    padding: 0px !important;
    margin: 0px !important;
  }

</style>
