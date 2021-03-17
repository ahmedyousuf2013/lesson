<template>
  <div id="app">
    <!-- 
    <plan-piker></plan-piker> -->
    <!-- <counter></counter> -->
    <!-- <button-counter>

    </button-counter> -->
    <!-- <plan  v-for="item in plans" v-bind:key="item" :name="item"></plan> -->

    <!-- <div v-text="message"></div> -->
    <!-- <div v-text="'hello ' + user.firstName + ' ' + user.lastName"></div> -->

    <!-- <div v-on:click = "clickHandler">ssssss</div> -->

    <!-- <span>{{message | uppercase}}</span> -->
    <!-- <span>{{ message | lowercase }}</span> -->
    <!-- <button v-on:click="deleteNinija">Delete ninija</button> -->

    <!-- <plog-post title="New Game"></plog-post> -->
    <!-- <plog-post
      v-bind:title="user.firstName + '  And last Name' + user.lastName"
      v-bind:like="8"
      v-bind:author="post"
    ></plog-post> -->

    <!-- simplest prop - pass a string -->
    <!-- <Child title="This is my title"></Child> -->

    <!-- Pass an object, defined inline -->
    <!-- <Child :parentData="{msg: 'xxx'}"></Child> -->

    <!-- Pass an object, defined in the `data()` method -->
    <!-- <Child :stringProp="myData"></Child> -->

    <!-- Pass a string variable, defined in `data()`. Note colon. -->
    <!-- <Child :stringProp="stringMessage"></Child> -->
    <!-- <about></about> -->
    <!-- <account-info username="matt" @changeUsername="changeUsername($event)"></account-info> -->
    <!-- <ul >
  <li v-for=" item in items" v-bind:key="item">
     {{item.childMsg }}
  </li>
</ul> -->
    <!-- <span v-once>{{ parentMsg}}</span> -->

    <!-- <span v-html="parentMsg"></span> -->

    <!-- <a v-bind:href="url">{{ linkText }}</a> -->
    <!-- <a :href="url">{{ linkText }}</a> -->
    <!-- <span v-text="name == Flavio ? 'Hi Flavio!' : 'Hi' + name + '!'"></span> -->

    <!-- <p v-if="shouldShowThis">Hey!</p> -->
    <!-- <a v-on:click="clickHandler">Click me!</a> -->
    <!-- <a  @click="clickHandler">Click me!</a> -->
    <div
      class="static"
      v-bind:class="{ active: isActive, 'text-danger': hasError }"
    ></div>
  </div>
</template>


<script>
import Counter from "./components/Counter.vue";
import ButtonCounter from "./components/Button.vue";
import plan from "./components/plan.vue";

import PlanPiker from "./components/PlanPiker";
import PlogPost from "./components/PlogPost.vue";

import Child from "./components/Child";

import about from "./components/Parent";
import AccountInfo from "./components/AccountInfo.vue";

export default {
  name: "app",
  components: {
    Counter,
    ButtonCounter,
    plan,
    PlanPiker,
    PlogPost,
    Child,
    about,
    AccountInfo,
  },
  // props:{
  //   ninjas:{
  //     type:Array,
  //     required:true
  //   }
  // },
  data() {
    return {
      message: "Welcome to Your Vue.js App",
      stringMessage: "test String message",
      user: {
        firstName: "Ahmed",
        lastName: "Mohamed",
      },
      url: "https://www.google.com.eg/webhp?tab=ww",
      parentMsg: "Hello",
      linkText: "Google",
      isActive: true,
      hasError: false,
      items: [{ childMsg: "Foo" }, { childMsg: "Bar" }],
      ninjas: [
        { name: "Ryu", speciality: "Vue Components", show: false },
        { name: "Crystal", speciality: "HTML Wizardry", show: false },
        { name: "Hitoshi", speciality: "Click Events", show: false },
        { name: "Tango", speciality: "Conditionals", show: false },
        { name: "Kami", speciality: "Webpack", show: false },
        { name: "Yoshi", speciality: "Data Diggin", show: false },
      ],
      Flavio: "Flavio",
      name: "Flavio",
      shouldShowThis: true,
      post: {
        id: 1,
        title: "My Journey with Vue",
      },
      myData: "My Data",
      boxes: [{ text: "sss" }],
    };
  },
  methods: {
    clickHandler() {
      alert("ok");
    },
    changeUsername(username) {
      debugger;
      this.user.username = username;
    },
    deleteNinija() {
      //this.boxes.shift();

      this.ninjas.pop();
    },
  },

  // beforeCreate() {
  //   alert("beforeCreated");
  // },

  // created() {
  //   alert("created");
  // },
  // beforeMount() {
  //   alert("beforeMount");
  // },
  // mounted() {
  //   alert("mounted");
  // },
  // beforeUpdate() {
  //   alert("beforeUpdate");
  // },
  // updated() {
  //   alert("updated");
  // },

  filters: {
    uppercase: function (value) {
      // if (!value) return ''
      return value.toUpperCase();
    },
    lowercase: function (value) {
      // if (!value) return ''
      return value.toLowerCase();
    },
  },
};
</script>

<style lang="scss">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1,
h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
