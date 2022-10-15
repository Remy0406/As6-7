<template>
  <navbar />
  <section class="home">

    <div class="image">
        <img src="images/image0.png" alt="">
    </div>

    <div class="content">
        <h3>{{name}}</h3>
        <span>{{motto}}</span>
        <p>{{content}}</p>
        <a href="about.html" class="btn"> about me <i class="fas fa-user"></i> </a>
    </div>

</section>
</template>

<script>
import Navbar from '../components/Navbar.vue'
export default {
  components: { Navbar },
      data() {
        return {
            name: "Panisara Hangwongngam",
            motto: "Sometimes I wish you never left",
            content: "have you ever been so close to someone that you were never in a relationship but when you both stopped talking it felt like a breakup",
        }
    }

}
</script>

<style>

</style>