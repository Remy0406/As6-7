<template>
    <div>
        <navbar />
         <section class="projects">
        <h1 class="heading"> <span>I like</span> this song </h1>
        <h3>{{project_name}}</h3>
        <p>{{project_detail}}</p>
        <div class="box-container">
            <iframe width="720" height="405" src="https://www.youtube.com/watch?v=mhIwoRk2K2E"
                title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; 
            gyroscope; picture-in-picture" allowfullscreen></iframe>
        </div>
    </section>
    </div>
</template>

<script>
import Navbar from '../components/Navbar.vue'
export default {
  components: { Navbar },
  data() {
        return {
            project_name:"Velika - U",
            project_detail:"Lyrics said My feel only one but I have no one",
        }
    }

}
</script>

<style>

</style>