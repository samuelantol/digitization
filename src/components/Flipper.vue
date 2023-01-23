<template>
    <h2> <button @click='selectTab(0)' :class="{selected: isSelected(0)}">Sken rukopisov</button> /
        <button @click='selectTab(1)' :class="{selected: isSelected(1)}">Sken viazaných kníh</button> /
        <button @click='selectTab(2)' :class="{selected: isSelected(2)}">Sken viazaných fotoalbumov</button> /
        <button @click='selectTab(3)' :class="{selected: isSelected(3)}">Sken architektonických výkresov</button> /
        <button @click='selectTab(4)' :class="{selected: isSelected(4)}">Sken obrazov s rôznym nasvietením</button> /
        <button @click='selectTab(5)' :class="{selected: isSelected(5)}">Sken textílií</button> </h2>

    <div class="flip-container">

        <div class="flip-button-left">
            <svg slot="handle" width="57" height="36" viewBox="0 0 57 36" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M21.4,32.3L7.2,18.1L21.4,4" stroke="#00FF00" stroke-width="10" />
            </svg>
        </div>

        <img class="page" src='https://images.unsplash.com/photo-1542216516-dc8bc35b0c97?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2804&q=80'>

        <div class="flip-button-right">
            <svg slot="handle" width="57" height="36" viewBox="0 0 57 36" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M35.4,4l14.1,14.1L35.4,32.3" stroke="#00FF00" stroke-width="10" />
            </svg>
        </div>

    </div>
</template>

<script setup>
    import { ref } from 'vue'

    const selected = ref(0);

    function selectTab (index) {
        selected.value = index;
    }

    function isSelected (index) {
        if (selected.value === index) {
            return true;
        } else {
            return false;
        }
    }
</script>

<style>
.flip-container {
    display: flex;
    flex-flow: row;
    align-items: center;
    justify-content: center;

    width: 100%;
    height: fit-content;
}
.page {
    display: inline-block;
    box-sizing: border-box;
    -moz-box-sizing: border-box;
    -webkit-box-sizing: border-box;
    width: 50vw;
    max-width: 500px;
    height: auto;
    border-left: 10px dashed #00ff00;
    border-right: 10px dashed #00ff00;
}
.flip-button {
    display: inline-block;
    width: 5%;
    height: 100%;
}
.selected {
    color: #000000;
}
</style>