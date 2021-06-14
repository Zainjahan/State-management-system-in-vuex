<template>
  <div>
      <h1 class="container">Vuex Counter</h1>
      <h1 class="container">{{counter}}</h1>
      <button @click="substractFromCounter(parseInt(value))">-</button>
      <input
   type="number"
   v-model="value"

      />
      <button  @click="addToCounter(parseInt(value))">+</button>
  <div>
  <button class="btn" @click="addRandomNumber">Add by Random Number</button>
  </div>
  </div>
  
</template>

<script>
import { mapState,mapMutations,mapActions} from "vuex"



export default {
  data(){
      return{
          value:1,
    
      }
  },
  methods:{
      ...mapMutations(["addToCounter","substractFromCounter"]),
      ...mapActions(["addRandomNumber"])
  },
  computed:{
      ...mapState(["counter"])
  }
}
</script>

<style>
.counter {
        font-size: 5rem;
        text-align: center;
    }
    button {
        border-radius: 100%;
        border: none;
        width: 2rem;
        height: 2rem;
        font-weight: 700;
        cursor: pointer;
    }
    input {
        padding: 0.4rem;
        margin: 0 0.5rem;
        text-align: center;
    }
    .btn {
        border-radius: 0.5rem;
        width: auto;
        background: #41B983;
        margin-top: 1rem;
        color: white;
        cursor: pointer;
    }
</style>
