<template>
  <div class="container">
    <form @submit.prevent="addSkill" autocomplete="off">
      <input
        type="text"
        placeholder="Enter a skill you have"
        v-model="skill"
        v-validate="'min:5'"
        name="skill"
      >
      <transition
        name="alert-in"
        enter-active-class="animated flipInX"
        leave-active-class="animated flipOutX"
      >
        <p class="alert" v-if="errors.has('skill')">{{errors.first('skill')}}</p>
      </transition>
    </form>
    <div class="holder">
      <ul>
        <transition-group
          name="item-in"
          enter-active-class="animated bounceInUp"
          leave-active-class="animated bounceOutDown"
        >
          <li v-for="(skill,index) in skills" :key="skill.skillName">
            {{skill.skillName}}
            <i class="fa fa-minus-circle" v-on:click="remove(index)"></i>
          </li>
        </transition-group>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "Skills",
  data() {
    return {
      skill: "",
      skills: [
        {
          id: 1,
          skillName: "react"
        },
        {
          id: 2,
          skillName: "vue"
        },
        {
          id: 3,
          skillName: "sass"
        }
      ]
    };
  },
  methods: {
    addSkill() {
      this.$validator.validateAll().then(result => {
        if (result) {
          this.skills.push({ skillName: this.skill });
          this.skill = "";
        } else {
          console.log("Not valid");
        }
      });
    },
    remove(id) {
      this.skills.splice(id, 1);
    }
  }
};
</script>

<style scoped>
@import "https://cdn.jsdelivr.net/npm/animate.css@3.5.1";
@import "https://maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css";

.holder {
  background: #fff;
  border-bottom-left-radius: 5px;
  border-bottom-right-radius: 5px;
}

form {
  position: relative;
}

ul {
  margin: 0;
  padding: 0;
  list-style-type: none;
}

ul li {
  padding: 20px;
  font-size: 1.3em;
  background-color: #42b883;
  border-left: 5px solid #35495e;
  margin-bottom: 2px;
  color: #fff;
}

ul li:last-child {
  border-bottom-left-radius: 5px;
  border-bottom-right-radius: 5px;
}

p {
  text-align: center;
  padding: 30px 0;
  color: gray;
}

.container {
  box-shadow: 0px 0px 40px lightgray;
  margin-top: 70px;
}

.fa-minus-circle {
  float: right;
  cursor: pointer;
}

input {
  width: calc(100% - 40px);
  border: 0;
  padding: 20px;
  font-size: 1.3em;
  background-color: #35495e;
  color: #fff;
  border-top-left-radius: 5px;
  border-top-right-radius: 5px;
}

.alert {
  background: #eb5a5a;
  font-weight: bold;
  display: inline-block;
  padding: 5px;
  margin-top: -20px;
  position: absolute;
  left: 0;
  width: calc(100% - 10px);
  top: 84px;
  color: #fff;
}

.alert-in-enter-active {
  animation: bounce-in 0.5s;
}

.alert-in-leave-active {
  animation: bounce-in 0.5s reverse;
}

.item-in-enter-active {
  animation: bounce-in 0.5s;
}

.item-in-leave-active {
  animation: bounce-in 0.5s reverse;
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
