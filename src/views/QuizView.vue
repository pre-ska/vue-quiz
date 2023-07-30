
<script setup>
    import { ref } from 'vue'
    import { useRoute } from 'vue-router';
    import q from '../data/quizzes.json'

    const quizzes = ref(q)

    const { params } = useRoute();

    const quizId = parseInt(params.id);

    const quiz = quizzes.value.filter(quiz => quiz.id === quizId)[0]
</script>

<template>
    <div v-if="quiz">
         <div  >
            {{quiz.text}}
        </div>
    </div>
</template>