<template>
    <div class="modal-container">
        <div class="modal">
            <h1>{{ header }}</h1>
            <p>{{ text }}</p>
        </div>
    </div>
</template>


<script>

    export default {
    props: [ 'header','text' ]
}
</script>  



<style scoped>
    .modal-container{
        width: 100%;
        padding: 1rem;
    }
    .modal{
    border-radius: 8px;
    border: 1px solid transparent;
    padding: 0.6em 1.2em;
    font-size: 1em;
    font-weight: 500;
    font-family: inherit;
    background-color: #1a1a1a;
    cursor: pointer;
    transition: border-color 0.25s;
    }
</style>
