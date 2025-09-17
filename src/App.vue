<template>
<h2>{{name}}</h2>
<div>
  <button v-on:mouseover="name = 'Batman'">Change to Batman</button>
  <button v-on:mouseover="changeName($event), increment(8, $event)">Change to Ashika</button>

</div>
<h2>{{ count }}</h2>
<button v-on:click="count += 1"> Increment </button>
<button v-on:click="count -= 1">Decrement</button>
<h2>{{ counts }}</h2>
<button @click="increment(8, $event)"> Increment by 8</button>
<button @click="decrement(2)">Decrement by 2</button>
</template>
<script>

export default {
  name: 'App',
  data() {
    return{
      name: "Ashika",
      count: 0,
      counts:0,
    }
     
  },
  methods:{
    increment(num, event){
      this.counts+=num
      console.log('Event', event)

    },
    decrement(num){
      this.counts-=num
    },
    changeName(event){
      this.name='Ashika'
      console.log('Event', event)
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.underline{
  text-decoration: underline;
}

.promoted{
  font-style: italic;
}

.new{
  color: green;
}

.sold-out{
  color: red;
}
</style>
