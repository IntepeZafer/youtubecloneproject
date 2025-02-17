<template>
    <form @submit.prevent="handleSubmit" class="formContainer">
        <input v-model="searchTerm" type="text" placeholder="Search">
        <button type="submit">Search</button>
    </form>
</template>

<script>
export default {
    emits : ['search'],
    name : 'SearchBarCompenent',
    data() {
        return {
            searchTerm : '',
        }
    },
    methods: {
        handleSubmit(){
            this.$emit('search', this.searchTerm)
        }
    }
}
</script>

<style scoped>
    .formContainer{
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
    }
    .formContainer  input{
        max-width: 90vw;
        width: 100%;
        border: 1px solid black;
        outline: none;
        padding: 0.5rem;
        border-radius: 0.3rem;
        border-top-right-radius: 0;
        border-bottom-right-radius: 0;
    }
    .formContainer button{
        max-width: 10vw;
        width: 100%;
        border: none;
        outline: none;
        padding: 0.5rem;
        cursor: pointer;
        background-color: black;
        color: white;
        border: 1px solid black;
        border-radius: 0.3rem;
        border-top-left-radius: 0;
        border-bottom-left-radius: 0;
    }
</style>