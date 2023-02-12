<template>
    <div> 
    <h1>
    movie

    </h1>
    <button @click="Network">name</button>
    <ul> <li v-for="movies in cartoon" :key="movies">
        {{ movies.id }}{{ movies.name }} {{ movies.status }}
        <h2> {{ movies.name}}</h2>
         <h4> {{ movies.species}}</h4>
         <h4> {{ movies.status}}</h4></li></ul>
    </div>
</template>
<script setup>
import axios from"axios";
import { ref } from"vue";


const cartoon = ref();
const url = ref("https://rickandmortyapi.com/api/character/108");
function Network() {
    axios    
    .get(url.value)    
    .then((response) => {
        cartoon.value = response.data;   
    })    
        .catch((err) => {console.log(err);    
        });
    }

</script>