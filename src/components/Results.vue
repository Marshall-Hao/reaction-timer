<template>
    <div class="grid justify-items-center">
        <p class="text-base font-medium">Reaction Time --- {{ score}} ms</p>
        <p class="mt-5 text-3xl text-indigo-500 font-bold">{{ rank }}</p>
    </div>
</template>

<script>
export default {
    props: ['score'],
    data() {
        return {
            rank: null
        }
    },
    mounted() {
        if (this.score < 250) {
            this.rank = "Ninja Fingers"
        } else if (this.score < 400) {
            this.rank = "Rapid Reflaxes"
        } else {
            this.rank = "snail pace.."
        }
    }
}
</script>