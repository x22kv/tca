<template>
  <div class="post">
    <div class="movie-card">
      <img :src="post.image" alt="Movie Poster">
      <h2>Название фильма: {{ post.title }}</h2>
      <p>Описание фильма: {{ post.body }}</p>
      <p>рейтинг фильма: {{ post.rating }}</p>
      <!-- <p>рейтинг фильма: {{ `../image/${post.image}` }}</p> -->
      <input v-model = 'newmark'>
      <button @click="addRating">Оценить</button>
      <h2>цена: {{ post.price }}р</h2>
      <button>Купить билет</button>
    </div>
  </div>
</template>



<script>
let n = 10;

export default{
    props:{
        post:{
            type:Object, 
            required: true,
        }
    }, 
    data(){
      return{
        newmark:""
      }
    },   
    methods:{
        addRating(){  
          this.$emit("addmark" , this.newmark)
          
        }

    }
}
</script>
<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    background-image: url("../image/bacground.jpg");
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;    
}
.App{
    padding: 20px;
}
.post {
  display: inline-block;
}

.movie-card {
  width: 300px;
  background-color: #fff;
  box-shadow: 0px 2px 10px rgba(0, 0, 0, 0.1);
  border-radius: 10px;
  overflow: hidden;
  margin: 20px;

}


.movie-card img {
  width: 100%;
  height: auto;
  display: block;
}

.movie-card h2 { 
  font-size: 20px;
  margin: 10px;
}

.movie-card p {
  font-size: 14px;
  margin: 10px;
}

.movie-card button {
  display: block;
  background-color: #3498db;
  color: #fff;
  border: none;
  border-radius: 5px;
  padding: 10px 15px;
  margin: 10px;
  font-size: 16px;
  cursor: pointer;
}
</style>
