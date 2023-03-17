<template>
    <div>
        <button :disabled="desactivar" @click="accion">{{ texto }}</button>
    </div>
</template>

<script>
export default {
    name: 'Vue3OptionApiCliAccionSaldo',

    props: {
        texto: String,
        desactivar: {
            type: Boolean,
            default: false
        }
    },


    data() {
        return {
            
        };
    },

    mounted() {
        
    },

    methods: {
        accion(){
            this.$emit('accion') //viene del @accion
        }
    },
};
</script>

<style  scoped>

</style>