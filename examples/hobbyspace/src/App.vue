<template>
  <div>
    <h2>Okestro Hobbyspace</h2>
    <button @click="displayHobbyInfo(hobbies[0])">01</button>
    <button @click="displayHobbyInfo(hobbies[1])">02</button>
    <button @click="displayHobbyInfo(hobbies[2])">03</button>
    <div v-if="displayedHobby">
      <h2>{{ displayedHobby.title }}</h2>
      <h3>{{ displayedHobby.date }}</h3>
      <h3>{{ displayedHobby.place }}</h3>
      <a v-bind:href="displayedHobby.link" target="_blank">More Info</a>
      
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      hobbies: [
        {
          title: "Adult Book Club",
          date: "on Thursday PM 7:00",
          place: "in Karajan",
          link: "https://www.notion.so/f9b1d93b5a254cf0bacd43ba598ae9eb?v=33584a8e9e1d42d5952b8a61aec12dd4",
        },
        {
          title: "Drink Eat Fourm",
          date: "on Friday PM 7:00",
          place: "TBD",
          link: "https://oil-lift-05f.notion.site/b3cbb58b1a6844faab69cc5ff10f991c?v=e0f9c3531c6b463bab15e39df4664cfc",
        },
        {
          title: "Gaming Human Inc",
          date: "on Saturday PM 7:00",
          place: "TBD",
          link: "https://oil-lift-05f.notion.site/5c87ad4af64a48138e514bb9ab137499?v=6d10e15b1fb849d18a4be87e5d82f42c",
        },
      ],
      displayedHobby: null,
    };
  },
  mounted() {
    this.displayedHobby = this.hobbies[0];
  },
  methods: {
    displayHobbyInfo(hobby) {
      this.displayedHobby = hobby;
    },
  },
};
</script>


<style>
body {
  display: flex;
  flex-direction: column;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.no_screen {
  display: none;
}
</style>
