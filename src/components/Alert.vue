<template>
    <div v-if="show" style="background: red; color: white">
        attenzione: {{ message }}
    </div>
</template>

<script>
import bus from '@/bus';

export default {
    data() {
        return {
            show: false,
            message: ''
        }
    },
    mounted() {
        bus.$on('alert', (args) => {
            this.show = true;
            this.message = args;
        });
    }
}
</script>