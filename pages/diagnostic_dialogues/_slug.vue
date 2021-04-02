<template>
    <div>

        <h1>Диагностический диалог</h1>

        <div v-if="showDialogue">

            <div v-if="showQuestion">
                <div v-if="currentQuestion.id === lastQuestion.id">
                    <h4>По всей видимости, Вам не удалось решить проблему самостоятельно.</h4>
                    <p>{{lastQuestion.answers.negative.action}} или начните диалог заново.</p>
                    <button class="btn btn-primary" @click="begin()">Начать заново</button>
                </div>
                <div v-else>
                    <h3>{{currentQuestion.text}}</h3>
                    <button class="btn btn-primary" @click="yes()">{{currentQuestion.answers.positive.text}}</button>
                    <button class="btn btn-danger" @click="no()">{{currentQuestion.answers.negative.text}}</button>
                </div>
            </div>

            <div v-if="!showQuestion">
                <h4>Что необходимо сделать</h4>
                <p>
                    {{currentQuestion.answers.negative.action}}
                </p>

                <div v-if="currentQuestion.id !== lastQuestion.id">
                    <h3>{{lastQuestion.text}}</h3>
                    <button class="btn btn-primary" @click="lastYes()">{{lastQuestion.answers.positive.text}}</button>
                    <button class="btn btn-danger" @click="lastNo()">{{lastQuestion.answers.negative.text}}</button>
                </div>

            </div>

        </div>
        <div v-else>
            <h3>Поздравляем, Вы решили проблему самостоятельно!</h3>
            <button class="btn btn-primary" @click="begin()">Начать заново</button>
        </div>
  
    </div>
</template>

<script>
export default {
    layout: 'docpage',
    methods:{
        getQuestionById(id){
            return this.questions.find(item => item.id === id)
        },
        yes(){
            this.showQuestion = true
            this.currentQuesitonId++
        },
        no(){
            this.showQuestion = false
        },
        lastYes(){
            this.showDialogue = false
        },
        lastNo(){
            this.yes()
        },
        begin(){
            this.currentQuesitonId = 1
            this.showDialogue = true
            this.showQuestion = true
        }
    },
    computed:{
        currentQuestion(){
            const question = this.getQuestionById(this.currentQuesitonId)
            return question
        },
        lastQuestion(){
            const question = this.getQuestionById(this.questions.length)
            return question
        }
    },
    data(){
        return{
            showDialogue: true,
            showQuestion: true,
            currentQuesitonId: 1,
        }
    },
    async asyncData({ $content, params }){
        const { questions } = await $content(`dialogues/${params.slug}`).fetch()
        return {questions}
    }
}
</script>