<template>
    <div v-if="showBlock" @click="stopTimer" class="block rounded-2xl p-36 text-5xl font-bold text-white bg-indigo-500 text-center">
        click me
    </div>
</template>

<script>
export default {
    props: ['delay'],
    data() {
        return {
            showBlock:false,
            timer: null,
            reactionTime: 0
        }
    },
    mounted() {
        setTimeout(() => {
           this.showBlock = true 
           this.startTimer()
        }, this.delay)
    },
    methods: {
        startTimer() {
            this.timer = setInterval(() => {
                this.reactionTime += 10
            }, 10)
        },
        stopTimer() {
            clearInterval(this.timer)
        },
    },
}
</script>