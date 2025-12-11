<template lang="">
    <div class="results">
        <h1 class="resultsTitle">Results</h1>
        <div>
            Correct answers {{ theQuestions.theQuestions.filter((ele) => {
                if(ele.correctAnswer == ele.selectAnswer) return true;
                return false
            }).length *2 }} / {{ theQuestions.theQuestions.length * 2 }}
        </div>
    </div>

</template>

<script setup>
const theQuestions = defineProps({
    theQuestions:{
        type:Object,
    }
})
</script>




<style lang="css">
    .results{
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        padding: 1.25rem; 
        max-width: 42rem; 
        text-align: center; 
        background-color: #ffffff; 

    }
    .resultsTitle{
        margin-bottom: 0.75rem; 
        font-size: 1.25rem;
        line-height: 1.75rem; 
    }
</style>