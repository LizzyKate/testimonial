<template>
  <div class="container-fluid">
  <div class="row max-height align-items-center">
   <!-- col -->
   <div class="col-10 mx-auto col-md-6">
    <div class="row">
     <div class="col text-center my-5">
      <h4 class="title-heading text-uppercase">client</h4>
      <h1 class="title-subheading text-uppercase">testimonials</h1>
     </div>
    </div>

    <div class="card my-5 text-center customer-card ">
     <img v-bind:src="('/img/' + first)" width="150" id="customer-img" class="img-card mx-auto" alt="">
     <h4 id="customer-name" class="text-uppercase">{{second}}</h4>
     <div class="review-icons my-2">
      <span class="star-icon">
       <i class="fas fa-star"></i>
      </span>
      <span class="star-icon">
       <i class="fas fa-star"></i>
      </span>
      <span class="star-icon">
       <i class="fas fa-star"></i>
      </span>
      <span class="star-icon">
       <i class="fas fa-star"></i>
      </span>
      <span class="star-icon">
       <i class="fas fa-star-half"></i>
      </span>
     </div>
     <p id="customer-text">{{text}}</p>
     <span class="quote-icon">
      <i class="fas fa-quote-left"></i>
     </span>
     <a href="#" class="btn prevBtn" v-on:click="btnLeft()"><i class="fas fa-chevron-left"></i></a>
     <a href="#" class="btn nextBtn" v-on:click="btnRight()"><i class="fas fa-chevron-right"></i></a>
    </div>
   </div>
   <!-- end of col -->
  </div>
 </div>


</template>

<script>
import  './assets/fonts/css/all.css'

export default {
 data(){
   return{
     first:'customer-0.png',
     text:'Lorem ipsum dolor sit amet consectetur adipisicing elit. Officiis neque reprehenderit laborum, corporis explicabo assumenda. Porro impedit consectetur animi, reprehenderit recusandae sapiente at aliquam reiciendis modi ipsam rerum suscipit distinctio?',
     second:'customer name',
     pictures:[ 'customer-1.png', 'customer-2.png', 'customer-3.png', 'customer-4.png'],
     name:['Jhon', 'Sandy', 'Amy', 'Tyrell', 'Wanda'],
     quote:[ 'Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old. Richard McClintock', 'There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injected humour, or randomised words which don\'t look even slightly believable.', 'If you are going to use a passage of Lorem Ipsum, you need to be sure there isn\'t anything embarrassing hidden in the middle of text.', 'Lorem Ipsum has been the industry\'s standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.'
     ],
     counter:0
   }
 },
 methods:{
   btnLeft(){
     this.counter--
     if(this.counter < 0){
       console.log('i am reducing')
       this.counter = this.pictures.length - 1;
       this.counter = this.name.length - 1;
       this.counter = this.quote.length - 1;
     }
    this.first = this.pictures[this.counter]
     this.second = this.name[this.counter];
     this.text = this.quote[this.counter];
     console.log('i was clicked')
   }, 
   btnRight(){
     this.counter++
     if(this.counter > this.pictures.length - 1){
       this.counter = 0
     }
      this.first = this.pictures[this.counter]
     this.second = this.name[this.counter];
     this.text = this.quote[this.counter];
   }
 }
}
</script>

<style>
.max-height{
 min-height: 100vh;
 background:linear-gradient(rgba(0,0,0,0.5),rgba(0,0,0,0.5)) ,url('/img/questionBcg.png')center/cover no-repeat fixed;
}
.title-heading{
 color:#f15025;
}
.title-subheading{
 color: white;
}
.customer-card{
 background: transparent!important;
 color:white;
 border:0.05rem solid white;
 padding-bottom: 1rem;
 padding-left: 1rem;
 padding-right: 1rem;
 position: relative;
}
.img-card{
 border-radius: 50%;
 margin-bottom: 1rem;
 margin-top: -3rem;
}
.star-icon{
 color: #f15025;
}
.quote-icon{
 font-size: 2rem;
 color: #f15025;
}
.prevBtn,.nextBtn{
 font-size: 1.5rem;
 padding: 0.1rem;
 color:#f15025;
 border:0.1rem solid #f15025;
 display: inline-block;
 position: absolute;
 padding: 0.4rem;
 border-radius: 50%;
 transition: all 1s ease-in-out;
}
.prevBtn:hover{
background: #f15025;
color: white;

}
.nextBtn:hover{
background: #f15025;
color: white;

}
.prevBtn{
 top: 50%;
 left: 0;
 transform: translate(-120%,-50%);
}
.nextBtn{
 top: 50%;
 right: 0;
 transform: translate(120%,-50%);
}
</style>
