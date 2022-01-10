<template>
    <div class="col-6">
        <button @click="handleAnswerClick(quiz[currentQuestion].answerOptions.isCorrect)">{{quiz[currentQuestion].answerOptions[index].answerText}}</button>
    </div>
</template>

<script>
import quiz from "../data/quiz";
export default {
  name: "Answers",
  props: [
    'index',
    'currentQuestion'
  ]
  ,
  data: function(){
    return{
      quiz,
    }
  },
  methods:{
    handleAnswerClick(isCorrect){
      this.$emit('update-question', isCorrect);
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
