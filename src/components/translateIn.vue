<template>
    <div id="translateIn">
    Translation
    <form v-on:submit="formSubmit">
        <input type="text" v-model="textoTraducir" placeholder="escriba la palabra">
        <input type="submit" value="traducir">
        <select v-model="idioma" id="">
            <option value="en">ingles</option>
            <option value="it">italiano</option>
        </select>
    </form>
    </div>
</template>

<script>
export default {
    name: "translateIn",
    data() {
        return{
            textoTraducir: '',
            idioma: ''
        }
    },
    created() {
        this.idioma = 'en';
    },
    methods: {
        formSubmit(e) {
            this.$emit('formSubmit',this.textoTraducir, this.idioma);
            e.preventDefault();
        }
    },
}
</script>

<style>

</style>