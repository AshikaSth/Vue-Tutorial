<template>
  <h2 v-for="(name, index) in names" :key="name">{{index}} {{ name }}</h2>
    <h2 v-for="name in fullNames" :key="name">{{name.first}} {{ name.last }}</h2>
<div v-for="actor in actors" :key="actor.name">
  <h2>{{ actor.name }}</h2>
  <h3 v-for="movie in actor.movies" :key="movie" >{{ movie }}</h3>
</div>
<h2 v-for="(value, key, index) in myInfo" :key="value"> {{ index }} {{ key }} {{ value }}</h2>
<template v-for="name in names" :key="name">
<h2>{{ name }}</h2>
<input placeholder="Last name">
<hr/>
</template>
<button @click="shuffle">Shuffle!</button>
</template>

<script>
import _ from "lodash";

export default {
  name: 'App',
  data() {
    return{
      names:['Bruce', 'Clark', 'Diana', 'Barry'],
      fullNames: [
        {first: 'Bruce', last: 'Wayne'},
        {first: 'Clarke', last: 'Kent'},
        {first: 'Princess', last: 'Diana'},
      ],
      actors: [
        {
          name: 'Christian Bale',
          movies: ['Batman', 'The Prestige'],
        }, 
        {
          name: 'Di Caprio',
          movies: ['Titanic', 'Inception'],
        },
      ],
      myInfo: {
        name: 'ashika',
        channel: 'Codevolution',
        course: 'Vue',
      }
    };
  },
  methods: {
    shuffle() {
      console.log(this.names);
      this.names = _.shuffle(this.names);
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
