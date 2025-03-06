<template>
  <div class="main">
  <questions-page v-if="currentQuestion <= questions.length-1" :theQuestions="questions[currentQuestion]" @on-answer-select ="answerSelect"
  @on-next-question="nextQuestion"/>
  <results-page v-else :theQuestions="questions"/>
  </div>
</template>




<script>
import questionsPage from '../components/questionsPage.vue';
import resultsPage from '../components/resultsPage.vue';

export default{
  components: { questionsPage,resultsPage },
  data() {
    return {
      currentQuestion: 0,  // Index
      questions:[
        {
          title: "Can I park here?",
          correctAnswer: 2,  // correct of array
          selectAnswer : null,  // index of answers array
          option:[
            "Sorry, I did that.",
            "It's the same place.",
            "Only for half an hour.",
          ]
        },
        {
          title: "What color will you paint the children's bedroom?",
          correctAnswer: 1,
          selectAnswer : null,
          option:[
            "I hope it was right.",
            "We can't decide.",
            "It wasn't very difficult.",
          ]
        },
        {
          title: "I can't understand this email.",
          correctAnswer: 0,
          selectAnswer : null,
          option:[
            "Would you like some help?",
            "Don't you know?",
            "I suppose you can.",
          ]
        },
        {
          title: "I'd like two tickets for tomorrow night.",
          correctAnswer: 2,
          selectAnswer : null,
          option:[
            "How much did you pay?",
            "Afternoon and evening.",
            "I'll just check for you.",
          ]
        },
        {
          title: "Shall we go to the gym now?",
          correctAnswer: 0,
          selectAnswer : null,
          option:[
            "I'm too tired.",
            "It's very good.",
            "Not at all.",
          ]
        },
        {
          title: "His eyes were ...... bad that he couldn't read the number plate of the car in front.",
          correctAnswer: 2,
          selectAnswer : null,
          option:[
            "such",
            "too",
            "so",
            "very",
          ]
        },
        {
          title: "The company needs to decide ...... and for all what its position is on this point.",
          correctAnswer: 1,
          selectAnswer : null,
          option:[
            "here",
            "once",
            "first",
            "finally",
          ]
        },
        {
          title: "Don't put your cup on the ...... of the table – someone will knock it off.",
          correctAnswer: 1,
          selectAnswer : null,
          option:[
            "outside",
            "edge",
            "boundary",
            "border",
          ]
        },
        {
          title: "I'm sorry - I didn't ...... to disturb you.",
          correctAnswer: 2,
          selectAnswer : null,
          option:[
            "hope",
            "think",
            "mean",
            "suppose",
          ]
        },
        {
          title: "The singer ended the concert ...... her most popular song",
          correctAnswer: 1,
          selectAnswer : null,
          option:[
            "by",
            "with",
            "in",
            "as",
          ]
        },
        {
          title: "Would you mind ...... these plates a wipe before putting them in the cupboard?",
          correctAnswer: 3,
          selectAnswer : null,
          option:[
            "making",
            "doing",
            "getting",
            "giving",
          ]
        },
        {
          title: "I was looking forward ...... at the new restaurant, but it was closed",
          correctAnswer: 2,
          selectAnswer : null,
          option:[
            "to eat",
            "to have eaten",
            "to eating",
            "eating",
          ]
        },
        {
          title: "...... tired Melissa is when she gets home from work, she always makes time to say goodnight to the children.",
          correctAnswer: 1,
          selectAnswer : null,
          option:[
            "Whatever",
            "No matter how",
            "However much",
            "Although",
          ]
        },
        {
          title: "It was only ten days ago ...... she started her new job",
          correctAnswer: 3,
          selectAnswer : null,
          option:[
            "then",
            "since",
            "after",
            "that",
          ]
        },
        {
          title: "The shop didn't have the shoes I wanted, but they've ...... a pair specially for me",
          correctAnswer: 1,
          selectAnswer : null,
          option:[
            "booked",
            "ordered",
            "commanded",
            "asked",
          ]
        }
      ]
    }
  },
  methods: {
    answerSelect(index){
      this.questions[this.currentQuestion].selectAnswer = index
    },
    nextQuestion(){
      this.currentQuestion++
    }
  },
}
 
</script>



<style lang="css">
  .main{
    display: flex; 
    align-items: center; 
    justify-content: center;
    width: 100vw; 
    height: 100vh; 
    background-color: rgba(0, 0, 0, 0.065); 
  }
  *{
    margin: 0%;
    padding: 0%;
    user-select: none;
  }
  body{
    box-sizing: border-box;
    font-family: Arial, Helvetica, sans-serif;
  }
</style>
