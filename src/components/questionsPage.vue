<template lang="">
    <div class="questionPage">
       <h1>{{ theQuestions.title }}</h1>
       <button class="option" :class="{ 'background-color-black': index === theQuestions.selectAnswer && theQuestions.selectAnswer !== null}" @click="$emit('on-answer-select',index)" v-for="(item,index) in theQuestions.option" :key="index">{{ item }}</button>
       <button class="next" @click="$emit('on-next-question',index)">Next question</button>
    </div>
</template>



<script>
export default {
    props:['theQuestions'],
    
}
</script>



<style lang="css">
   .questionPage{
    display: flex ;
    flex-direction: column;
    padding: 1.25rem; 
    max-width: 42rem; 
    text-align: center; 
    background-color: #ffffff; 
    justify-content: center;
    align-items: center;
   }
   h1{
    margin-bottom: 0.75rem; 
    font-size: 1.25rem;
    line-height: 1.75rem; 
   }
   .option{
    padding-top: 0.75rem;
    padding-bottom: 0.75rem; 
    padding-left: 2.5rem;
    padding-right: 2.5rem; 
    margin-bottom: 0.5rem; 
    width: 100%; 
    background-color: #F3F4F6; 
    cursor: pointer;
    border-style:none;
    transition: 0.3s ease;
   }
   .option:hover{
    background-color:rgba(0, 0, 0, 0.316);
   }
   .next{
    padding-top: 0.75rem;
    padding-bottom: 0.75rem; 
    margin-top: 1rem; 
    width: 100%; 
    color: #ffffff; 
    background-color: #3B82F6;
    border-style:none ;
    cursor: pointer;
   }
    .background-color-black {
        background-color: rgba(0, 0, 0, 0.333);
    }
</style>