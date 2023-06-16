<template>
  <Header />
  <main>
    <Cards />
  </main>
</template>

<script>
import Header from "./components/Header.vue";
import Cards from "./components/Cards.vue";
export default {
  components: {
    Header,
    Cards,
  },
};
</script>

<style lang="css" scoped></style>
