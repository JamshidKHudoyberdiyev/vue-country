<template>
  <header class="flex items-center">
    <div class="container flex items-center justify-between">
      <h1 class="font-extrabold text-[#111517] text-[24px]">
        Where in the world?
      </h1>
      <div class="darkmode flex gap-2">
        <span><i class="bx bx-moon"></i></span>
        <p>Dark Mode</p>
      </div>
    </div>
  </header>
</template>

<script>
export default {};
</script>

<style lang="css" scoped>
header {
  /* width: 1440px; */
  height: 80px;
}
.container {
  max-width: 1280px;
  margin: 0 auto;
  width: 100%;
}
header {
  background: #ffffff;
  box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.0562443);
}
</style>
