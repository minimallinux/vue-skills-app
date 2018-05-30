<template>
  <div id="app">
  <Skills msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import Skills from './components/Skills.vue'

export default {
  name: 'app',
  components: {
    Skills
  }
}
</script>
<style>
@import "https://cdn.jsdelivr.net/npm/animate.css@3.5.1";
body {
font-family: 'Verdana', sans-serif;
 display:grid;
 grid-template-rows:auto;
 justify-items:center;
 align-items:center;
}
body, html {
margin:0;
height:100%;
}
#app {
width:50%;
}
ul {
padding:0px;
list-style-type:none;
}
ul li {
padding:20px;
font-size: 1.3em;
background-color:#e0edf4;
border-left:5px solid #3eb3f6;
margin-bottom:2px;
color:#3e5252;
}
p {
text-align:center;
padding:30px 0;
background: whitesmoke;
color:gray;
}
.container {
box-shadow:0px 0px 40px lightgrey;
}
input {
color:white;
background: black;
width:200px;
padding:10px;
}
.center {
text-align:center;
}
.alert {
font-weight:bold;
display:inline-block;
padding:5px;
margin-top: -20px;
background: #fdf2ce;
}
.alert-in-enter-active {
animation:bounce-in .5s;
}
.alert-in-leave-active {
animation:bounce-in .5s reverse ; 
}
@keyframes bounce-in {
0% {
transform: scale(0);  
}
50% {
transform: scale(1.5);
}
100% {
transform: scale(1);
}
}
</style>
