<template>
    <div v-if="showBlock" class="block rounded-2xl p-36 text-5xl font-bold text-white bg-indigo-500 text-center">
        click me
    </div>
</template>

<script>
export default {
    props: ['delay'],
    data() {
        return {
            showBlock:false
        }
    },
    mounted() {
        setTimeout(() => {
           this.showBlock = true 
        }, this.delay)
    },
}
</script>