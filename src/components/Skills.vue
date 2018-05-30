<template>
  <div class="hello">
  <div class="holder">
  <h2 class="center">Skills</h2>
  <div class="center">
  <form @submit.prevent="addSkill">
  <input type="text" placeholder="Enter a skill you have.." v-model="skill" v-validate="'min:5'" name="skill">
  <input type="checkbox" id="checkbox" v-model="checked">
  <transition name="alert-in" enter-active-class="animated-flipinx" leave-active-class="animated-flipoutx">
  <p class="alert" v-if="errors.has('skill')">{{ errors.first('skill')}}</p>
  </transition>
  </form>
  </div>
  <ul>
  <li v-for="(data, index) in skills" :key='index'>{{ data.skill}}</li>
   </ul> 
  <p>These are the skills that you possess!</p>
 </div>
 </div>
</template>

<script>
export default {
  name: 'Skills',
  data() {
    return {
    checked:false,
    skill:"",
    skills: [
    { "skill": "Vue JS"}
    ]
    }
    },
    methods: {
    addSkill() {
    this.$validator.validateAll().then((result) => {
    if(result) {
    this.skills.push({skill:this.skill})
    this.skill = "";
    } else {
    // eslint-disable-next-line no-console  
    console.log('Not Valid');
    }
    })
}
},
}
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<!--<style src="./Skills.css">
</style>-->
<style scoped>
@import "https://cdn.jsdelivr.net/npm/animate.css@3.5.2/animate.min.css";
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
.alert-in .enter-active {
animation:bounce-in .5s;
}
.alert-in .leave-active {
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
