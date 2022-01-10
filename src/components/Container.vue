<template>
  <div class="quiz">
    <!-- <h1>{{ msg }}</h1> -->
    <div class="container">
      <div class="row">
        <Questions :currentQuestion="currentQuestion"/>
      </div>
      <div class="row">
        <Answer :key="index" v-for="(option, index) in quiz[currentQuestion].answerOptions" :index="index" :currentQuestion="currentQuestion" @update-question="updateQuestion(option.isCorrect)"/>
      </div>
        <!-- <div v-for="(question, index) in questions" :key="index" class="col-12">
          <h2>{{ question.question }}</h2>
        </div>   -->
        <!-- <div v-for="question in questions" :key="index" class="col-6">
          <h3> {{ questions.answer_1 }}</h3>
        </div> -->
    </div>
  </div>
</template>

<script>
import Questions from "./Questions.vue";
import Answer from "./Answer.vue";
import quiz from "../data/quiz";

export default {
  name: "Container",
  components: {
    Questions,
    Answer,
  },
  data: function(){
    return{
      currentQuestion:0,
      score:0,
      quiz,
    }
  },
  methods:{
        updateQuestion(isCorrect){
            let nextQuestion = this.currentQuestion + 1;
            if(isCorrect){
                this.score = this.score + 1;
                console.log("score:"+this.score);
            }
            if(nextQuestion < this.quiz.length && isCorrect){
            this.currentQuestion = nextQuestion;
            console.log("question n. " + this.currentQuestion);
            }
            else{
              alert("YOU LOSE!");
              this.currentQuestion = 0;
            }
        },
    },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../style/general.scss";

.quiz {
  background-color: #11093a;
  height: calc(100vh - 450px);
  h1,
  h2,
  h3 {
    color: white;
    padding: 0px !important;
    margin: 0px !important;
  }
}
</style>
