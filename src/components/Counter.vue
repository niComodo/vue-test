<template>
    <div style="border: 1px solid gray; padding: 10px; margin: 20px 0;">
        <div>qta: {{ count }}</div>

        <div>tot: {{ total }}</div>

        <a href="#" @click.prevent="incrementa">piu'</a>
        <a href="#" @click.prevent="decrementa">meno</a>
    </div>
</template>

<script>
export default {
    data() {
        return {
            count: this.value,
        }
    },
    // props: [
    //     'price',
    // ],
    // props prende valori dall'esterno'
    props: {
        price: {
            default: 30,
            type: Number,
        },
        value: {
            default: 1,
            type: Number,
        },
    },
    methods: {
        incrementa() {
            this.count++
        },
        decrementa() {
            this.count--
        }
    },
    computed: {
        total() {
            return this.count * this.price;
        }
    },
    watch: {
        count(value) {
            console.log(value);
            this.$emit('input', value)
        },
        value(value) {
            this.count = value;
        },
    }
}
</script>

<style scoped>

</style>