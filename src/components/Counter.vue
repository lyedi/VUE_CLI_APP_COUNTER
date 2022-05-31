<template>
  <h1> {{customTitle}}</h1>
    <p> {{counter}} <sup> 2</sup> ={{squareCounter}} </p>

    <button v-on:click="increase()" >+</button>
    <button v-on:click="decrease" >-</button>
  <!-- <p> {{counter}} <sup> 2</sup> ={{getSquareValue()}} </p> -->
   <!-- <p> {{counter}} <sup> 2</sup> ={{counter * counter}} </p> -->

   <!-- <p> {{counter}} <sup> 2</sup> ={{squareCounter}} </p>
   <p> {{counter}} <sup> 2</sup> ={{squareCounter}} </p>
   
   <p> {{counter}} <sup> 2</sup> ={{squareCounter}} </p>
   <p> {{counter}} <sup> 2</sup> ={{squareCounter}} </p> -->
    <!-- <p> {{counter}} <sup> 2</sup> ={{counter * counter}} </p> -->

  <!-- <div> {{counter}} </div> -->

  
</template>

<script>
export default {
//   props: ['title', 'start'],
    props:{
        title: String,
        start:{
            type:  Number,
            default: 10,
            validator(value){
                return value >=0
            }
            // required: true
        }
    },
    data() {
        return {
            counter: this.start
        }
  },
  methods: {
      getSquareValue(){
          console.log('getSquareValue')
          return this.counter * this.counter
      },
      increase(){ 
          this.counter++

      },
      decrease(){
          this.counter--

      }

  },
  computed:{
      squareCounter(){
          console.log('computed squareCounter')
          return    this.counter * this.counter
      },
      customTitle(){
        //   return this.title ? this.title : 'Counter'
          //   return this.title || 'Counter'
          if(this.title !== undefined){
              return this.title
          }
          else{
              return 'Counter'
          }
        //   console.log(this.title)
        //   return  this.title
      }
  }
}
</script>

<style>
button{
    background-color: #64b687;
    border-radius: 5px;
    border: 1px solid white;
    color: white;
    cursor: pointer;
    margin:0 5px;
    padding: 5px 15px;
    transition: 0.2s ease-in-out;

}

button:hover{
    background-color: aqua;
    transition: 0.3s ease-in-out;
}
</style>