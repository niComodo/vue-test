<template>
    <div style="border: 1px solid gray; padding: 10px; margin: 20px 0;">
        <div>qta: {{ value }}</div>

        <a href="#" @click.prevent="incrementa">piu'</a>
        <a href="#" @click.prevent="decrementa">meno</a>
    </div>
</template>

<script>
import bus from '@/bus';

export default {
    props: {
        value: {
            default: 1,
            type: Number,
        },
    },
    methods: {
        incrementa() {
            this.$emit('input', this.value + 1)

            if (this.value + 1 === 5) {
                bus.$emit('alert', 'numero = 5');
            }
        },
        decrementa() {
            this.$emit('input', this.value - 1)
        }
    },
}
</script>

<style scoped>

</style>