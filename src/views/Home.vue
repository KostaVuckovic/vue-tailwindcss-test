<template>
  <main class="home pt-24 flex flex-col items-center font-body ">
    <section>
      <h1 class="hero-title text-6xl mx-4 font-bold text-center font-body leading-tight tracking-tighter md:text-7xl lg:text-8xl">Mobility of Tomorrow</h1>
      <div>
        <img src="@/assets/hero-image.jpg" alt="" class="">
      </div>
    </section>
  </main>
</template>

<script>

export default {
  name: 'Home',
  components: {
  }
}
</script>

<style scoped>
@media screen and (min-width: 1392px) {
  .hero-title{
    font-size: 120px;
  }
}
</style>
