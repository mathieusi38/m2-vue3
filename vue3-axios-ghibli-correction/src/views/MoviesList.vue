<script setup>
import { onBeforeMount, ref } from 'vue'
import axios from 'axios'

const API_ALL_FILMS = 'https://ghibliapi.herokuapp.com/films'

const movies = ref([])


onBeforeMount(async ()=>{
    console.log('ON BEFORE MOUNT')
    const allFilms = await axios.get(API_ALL_FILMS)
    const {data} = allFilms
    movies.value = data
})


</script>

<template>
  <div class="container">
        <!-- component with nested async dependencies -->
        <table class="styled-table">
            <thead>
                <tr>
                    <th>Id</th>
                    <th>Name</th>
                    <th>Year</th>
                    <th>Voir</th>
                </tr>
            </thead> 
            <tbody>
                
                <tr v-for="movie in movies">
                    <td>{{movie.id}}</td>
                    <td>{{movie.title}}</td>
                    <td>{{movie.release_date}}</td>
                    <td >👀</td>
                </tr>
            </tbody>
        </table>

        
    </div>
</template>

<style>
div.container{
    font-family: 'Muli', sans-serif;
	display: flex;
	align-items: center;
}

.styled-table {
    margin-left: auto;
    margin-right: auto;
    border-collapse: collapse;
    font-size: 0.9em;
    font-family: sans-serif;
    min-width: 920px;
    box-shadow: 0 0 20px rgba(0, 0, 0, 0.15);
}
.styled-table thead tr {
    background-color: #009879;
    color: #ffffff;

}
.styled-table th,
.styled-table td {
    padding: 12px 15px;
}
.styled-table tbody tr {
    border-bottom: 1px solid #dddddd;
}

.styled-table tbody tr:nth-of-type(even) {
    background-color: #f3f3f3;
}

.styled-table tbody tr:last-of-type {
    border-bottom: 2px solid #009879;
}

.styled-table tbody tr.active-row {
    font-weight: bold;
    color: #009879;
}

</style>
