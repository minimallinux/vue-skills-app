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


</style>
