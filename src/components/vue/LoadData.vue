<script setup>
import {ref} from 'vue'

const users = ref([])




function LoadData (){

    fetch('https://jsonplaceholder.typicode.com/users')
        .then(function(response)  {
            return response.json()
        })
        .then(function (data){
            console.log(data);
            users.value = data
        })
   


}


</script>

<template >

    <div class="bg-slate-300 mb-1 mt-4  " v-for="user in users " :key="users.id">{{ user.name }}</div>
    <button class="bg-red-400 mx-auto flex"  @click="LoadData">
        cargar info
    </button>
      
    
</template>