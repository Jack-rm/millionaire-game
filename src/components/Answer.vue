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
        // startQuizFunc(){
        //     this.startQuiz = true
        //     this.countDownTimer()
        // },

        handleAnswerClick(isCorrect){
            // clearTimeout(this.timer);
            let nextQuestion = this.currentQuestion + 1;
            if(isCorrect){
                this.score = this.score + 1;
            }
            if(nextQuestion < this.quiz.length){
            this.currentQuestion = nextQuestion;
            // this.$store.state.questionAttended = this.currentQuestion;
            // localStorage.setItem('qattended', this.currentQuestion)
            // this.countDown = 30;
            // this.countDownTimer();
            }
            else{
                // localStorage.removeItem('qattended')
                // this.showScore = true;
                // localStorage.setItem('testComplete',this.showScore)
            }
        },
        // countDownTimer() {
        //         if(this.countDown > 0) {
        //             this.timer = setTimeout(() => {
        //                 this.countDown -= 1
        //                 this.countDownTimer()
        //             }, 1000)
        //         }
        //         else{
        //             this.handleAnswerClick(false)
        //         }
        //     }
    },
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
