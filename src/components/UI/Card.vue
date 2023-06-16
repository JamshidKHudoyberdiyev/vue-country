<template>
  <div class="card">
    <img :src="country.flag" alt="" />
    <div class="card_info p-[24px]">
      <h3 class="countryname pb-4">{{ country.name ?? "CountryName" }}</h3>
      <ul class="info list-none flex flex-col gap-y-2">
        <li class="info_item">
          Population:<span>{{ country.population ?? "population" }}</span>
        </li>
        <li class="info_item">
          Region:<span>{{ country.region ?? "Region" }}</span>
        </li>
        <li class="info_item">
          Capital:<span>{{ country.capital ?? "Capital" }}</span>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    country: Object,
    // img: String,
    // countryName: String,
    // population: Number,
    // region: String,
    // capital: String,
  },
};
</script>

<style lang="css" scoped>
.card {
  font-family: "Nunito Sans", sans-serif;
  height: 336px;
  width: 264px;
  background: #ffffff;
  box-shadow: 0px 0px 7px 2px rgba(0, 0, 0, 0.0294384);
  border-radius: 5px;
}
.countryname {
  font-style: normal;
  font-weight: 800;
  font-size: 18px;
  line-height: 26px;
  /* identical to box height, or 144% */

  color: #111517;
}
.info_item {
  font-family: "Nunito Sans";
  font-style: normal;
  font-weight: 600;
  font-size: 14px;
  line-height: 16px;
  /* identical to box height, or 114% */

  color: #111517;
}
.info_item span {
  font-weight: 400;
}
</style>
