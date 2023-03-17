<template>
    <div>
        <h2>Tipo de Cuenta: {{ cuenta }}</h2>
        <h2>Saldo: {{ saldo }} </h2>
        <h2>Cuenta {{ estado ? 'Activa' : 'Desactivada' }}</h2>
        <div v-for="(item, index) in servicios" :key="index">
            {{ index +1 }} - {{ item }}
        </div>
        <!-- accion -> para la comunicación del hijo al padre -->
        <AccionSaldo :desactivar="desactivar" texto="Disminuir Saldo" @accion="disminuir"></AccionSaldo>
        <AccionSaldo texto="Aumentar Saldo" @accion="aumentar" ></AccionSaldo>
    </div>
</template>

<script>
import AccionSaldo from './AccionSaldo.vue';

export default {
    name: 'Vue3OptionApiCliCuenta',

    components:{
        AccionSaldo
    },

    data() {
        return {
            saldo: 1000,
            desactivar: false,
            cuenta: 'Visa',
            estado: true,
            servicios: ['giro', 'abono', 'transferencia']
        };
    },

    mounted() {
        
    },

    methods: {
        aumentar(){
            this.saldo = this.saldo + 100
            this.desactivar = false;
        },
        disminuir(){

            if(this.saldo == 0){
                this.desactivar = true;
                alert('Saldo agotado');
                return
            }
            this.saldo = this.saldo - 100
        }
    },
};
</script>

<style lang="scss" scoped>

</style>