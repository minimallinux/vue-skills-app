<template>
  <div id="app">
<nav>
  <router-link to="/">Home</router-link>
   <router-link to="/about">About</router-link>
</nav>
<router-view />
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
body {
font-family: 'Verdana', sans-serif;
 display:grid;
 grid-template-rows:auto;
 justify-items:center;
padding-top:50px;
}
body, html {
margin:0;
height:100%;
}
#app {
width:50%;
}
nav {
padding:20px 20px 20px 0;
}
nav a {
padding: 10px;
text-decoration: none;
background: #fff;
border-radius: 3px;
color:#3eb3f6;
font-weight: bold;
margin-right: 15px;
}
</style>
