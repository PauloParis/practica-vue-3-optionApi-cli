<template>
    <div>
        <h1>{{ texto }}</h1>
    </div>
</template>

<script>
export default {

    name: 'Vue3OptionApiCliTitulo',
    props: {
        texto: String
    },
    data() {
        return {
            
        };
    },

    mounted() {
        
    },

    methods: {
        
    },
};
</script>

<style scoped> /* scoped -> los estilos solo funcionan en este componente */

h1 {
    color: peru;
}
</style>