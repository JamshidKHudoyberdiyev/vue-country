<script>
import Card from "./UI/Card.vue";

export default {
  data() {
    return {
      countries: [],
      load: true,
      inputVlue: "",
    };
  },

  methods: {
    async getData() {
      let k = await fetch("https://restcountries.com/v2/all");
      k = await k.json();
      this.countries = k;
      this.load = false;
      //   console.log(this.countries);
    },
    async getInputvalue() {
      let filtrname = await fetch(
        `https://restcountries.com/v3.1/name/${this.inputVlue}`
      );
      filtrname = await filtrname.json();
      console.log(filtrname);
      this.countries = filtrname;
    },
  },
  mounted() {
    this.getData();
    console.log(this.countries);
  },

  components: { Card, Card },
};
</script>

<template>
  <div class="container pt-[48px]">
    <div class="search flex justify-between pb-12">
      <input
        v-model="inputVlue"
        v-on:input="getInputvalue"
        type="text"
        class="w-[480px] h-[56px] pl-[32px] py-[18px] outline-none rounded"
        placeholder="Search for a country…"
      />
      <select class="w-[200px] h-[56px] outline-none px-[18px]">
        <option selected>Choose a country</option>
        <option value="US">United States</option>
        <option value="CA">Canada</option>
        <option value="FR">France</option>
        <option value="DE">Germany</option>
      </select>
    </div>
    <div class="cards flex flex-wrap gap-[60px]">
      <div v-if="load" class="loading"></div>
      <!-- <h1 v-for="(item, index) in countries">{{ item.name }}</h1> -->
      <Card v-for="(card, index) in countries" :country="card" />
    </div>
  </div>
</template>

<style lang="css" scoped>
.container {
  max-width: 1280px;
  margin: 0 auto;
  width: 100%;
}
input {
  background: #ffffff;
  box-shadow: 0px 2px 9px rgba(0, 0, 0, 0.0532439);
  border-radius: 5px;
}
select {
  background: #ffffff;
  box-shadow: 0px 2px 9px rgba(0, 0, 0, 0.0532439);
  border-radius: 5px;
}
.loading {
  height: 0;
  width: 0;
  padding: 15px;
  border: 6px solid #ccc;
  border-right-color: #888;
  border-radius: 22px;
  -webkit-animation: rotate 1s infinite linear;
  /* left, top and position just for the demo! */
  position: absolute;
  left: 50%;
  top: 50%;
}

@-webkit-keyframes rotate {
  /* 100% keyframe for  clockwise. 
     use 0% instead for anticlockwise */
  100% {
    -webkit-transform: rotate(360deg);
  }
}
</style>
