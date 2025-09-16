<template>
<div>
<div> {{greet}} {{ name }}</div>
<div v-html="channel"></div>
<div >{{channel}}</div>
<div v-html="hack"></div>
<div :id="headingId"><h2>Heading</h2></div>
<button :disabled="isDisabled">Bind</button>
<h2 class="underline">Underline</h2>
<h2 class="underline" :class=" status">Status</h2>
<h2 :class="isPromoted && 'promoted'" >Promoted Movie</h2>
<h2 :class="isSoldout? 'sold-out' : 'new'">Soldout? movie</h2>
<h2 :class="['new', 'promoted']">Newly Promoted movie</h2>
<h2 :class="[ isPromoted && 'promoted', isSoldout? 'sold-out' : 'new']">Array conditional movie</h2>
<h2 :class="{
  promoted: isPromoted,
  new: !isSoldout,
  'sold-out': isSoldout,
}">Object Conditional Movie</h2>
<h2 :style="{
  color: highlightColor,
  'font-size': headerSize + 'px',
  padding: '20px',
  }">Inline Style</h2>
  <h2 :style="headerStyleObject">Style Object</h2>
  <div :style="[baseStyleObject, successStyleObject]">SuccessStyle</div>
  <div :style="[baseStyleObject, dangerStyleObject]">Danger Style</div>

</div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return{
      greet: "Hello",
      name: "Batman",
      channel: "<b>Codevolutiion</b>",
      hack: `<a href="#" onclick="alert('You have been hacked!')">Win a prize!</a>`,
      headingId:'heading',
      isDisabled: true,
      status: 'success',
      isPromoted: true,
      isNew:true,
      isSoldout: true,
      highlightColor: 'orange',
      headerSize: 50,
      headerStyleObject: {
        color:'orange',
        fontSize: '50px',
        padding: '20px',
      },
      baseStyleObject: {
        fontSize:'50px',
        padding:'10px',
      },
      successStyleObject: {
        color: 'green',
        backgroundColor: 'lightGreen',
        border: '1px solid green',
        padding: '20px',
      },
      dangerStyleObject: {
         color: 'darkred',
        backgroundColor: 'red',
        border: '1px solid darkred',
      }
    };
  },
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
