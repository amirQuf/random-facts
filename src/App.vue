<script>
import axios from 'axios'

export default {
  data(){
    return{
      erorr:false,
      isloading:false,
      info:{},
    }
  },
  filters: {
 decimal (value) { 
    return value.toFixed(2)
  }
},
  methods:{
    async fetch(){
    const  url = "https://api.adviceslip.com/advice"
    axios
  .get(url )
  .then(response => (this.info = response.data.slip  
  ))
  .catch(error => this.erorr=true)
  console.log(this.info)
  
    }
  },
  mounted(){
    console.log("start")
    this.fetch()
  
  },
}
</script>

<template>
  <div class = "flex">
    <div class ="card">
  <div class ="card-body">

    <h4 class="card-title">ADVICE  #{{ info["id"]}}</h4>
    <p class="card-text">{{ info["advice"] }}<br></p></div>
    <div class="dice" @click="fetch" ><img src="icon-dice.svg" alt="" srcset=""></div>
  
</div>
    </div>
 
  
</template>

<style>
.flex{
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  color:hsl(217, 19%, 38%); 
 
}
.card-title{
  color:hsl(150, 100%, 66%);
  text-align: center;
  font-size: 24px;
  justify-content: center;
  font-family: 'Manrope', sans-serif;
  font-family: 'Poppins', sans-serif;

}
/* - Light Cyan: hsl(193, 38%, 86%)
- Neon Green: hsl(150, 100%, 66%)

### Neutral

- Grayish Blue: 
- Dark Grayish Blue: 
- Dark Blue: hsl(218, 23%, 16%) */
.card{
  background-color: hsl(217, 19%, 24%)!important;
  /* box-shadow: 0 0px 20px 0 hsl(217, 19%, 24%); */
  
  padding: 10px;
  align-self: center;
  width: 80%;
  height:  130px;
  border-radius: 10px;
  padding-left: 50px;
  padding-right: 20px;
  position:absolute;
  top: 50%;
  left:50%;
  
}
@media screen(min-lenght=375px) {
  .card{
  
  width: 50%;
  height: 50%;

  }
  
}

.btn{
  color:hsl(150, 100%, 66%);
}
p{

  text-align: center;
  text-align: justify;
  font-size: 28px;
  font-family: 'Manrope', sans-serif;
  font-family: 'Poppins', sans-serif;
  font-weight: 800;
  
  color: white!important;;

}
img{
  margin-top: 4px;
  margin-bottom: 4px;
}

.dice{
  color: hsl(150, 100%, 66%)!important;
  background-color:  hsl(150, 100%, 66%)!important;
  text-align: center;
  border-radius:50%;
  width:80px; 
  height:80px;
  position:absolute;
  top: 80%;
  left:50%;
  
}

</style>