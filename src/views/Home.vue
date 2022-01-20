<template>
  <ul class="ul">
    <Loader v-if="loader"/>
    <Beers v-else v-bind:beer="beer"/>
    <div class="div">
      <button class="button" v-on:click='getBeer'>Хочу другое пиво</button>
    </div>
  </ul>
</template>

<script>

import Beers from '../components/Beers.vue'
import Loader from '../components/Loader.vue'

 export default {
    name: 'Beer',
    components: {
      Beers,
      Loader
    },
    data() {
      return {
        beer: {},
        loader: false
      }
    },
    methods: {
      getBeer() {
        fetch('https://random-data-api.com/api/beer/random_beer')
          .then(data => data.json())
          .then(data => {
            this.loader = true
            setTimeout(() => {
              this.beer = data
              this.loader = false
            }, 1000)
            
          }
          )
      }
    },
    mounted() {
      fetch('https://random-data-api.com/api/beer/random_beer')
          .then(data => data.json())
          .then(data => this.beer = data)
          
        }
    }
</script>

<style >
.ul {
  padding: 30px 0 20px 0;
  list-style-type: none;
  width: 100%;
  max-width: 600px;
  height: 600px;
  max-height: 600px;
  margin: auto;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.div {
  display: flex;
  justify-content: center;
}

.button {
  border: none;
  outline: none;
  background-color: #42b983;
  width: 200px;
  padding: 10px;
  border-radius: 10px;
  font-size: 22px;
  font-weight: 500;
  color: white;
  cursor: pointer;
  transition: .3s ease-in-out;
}

@keyframes animate {
  0% {
    transform: scale(1);
  }

  100% {
    transform: scale(1.1);
  }
}

.button:hover {
  animation: animate .3s alternate;
  animation-iteration-count: 4;
}

.button:focus {
  animation: animate .3s alternate;
  animation-iteration-count: 4;
}


</style>
