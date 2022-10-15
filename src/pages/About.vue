<template>
    <div>
        <navbar />
        <section class="about">

            <h1 class="heading"> about <span>me</span> </h1>

            <div class="row">

                <div class="info-container">

                    <h1>personal info</h1>

                    <div class="box-container">

                        <div class="box">
                            <h3> <span>name : </span>{{name}}</h3>
                            <h3> <span>age : </span>{{age}}</h3>
                            <h3> <span>email : </span>{{email}}</h3>
                            <h3> <span>address : </span>{{address}}</h3>
                        </div>

                        <div class="box">
                            <h3> <span>freelance : </span>{{freelance}}</h3>
                            <h3> <span>skill : </span>{{skill}}</h3>
                            <h3> <span>experience : </span>{{experience}}</h3>
                            <h3> <span>language : </span>{{language}}</h3>
                        </div>

                    </div>

                    
                    

                </div>

                <div class="count-container">

                    <div class="box">
                        <h3>2+</h3>
                        <p>months of experience</p>
                    </div>

                    <div class="box">
                        <h3>10+</h3>
                        <p>happy clients</p>
                    </div>

                    <div class="box">
                        <h3>20+</h3>
                        <p>project completed</p>
                    </div>

                    <div class="box">
                        <h3>5 baht each question</h3>
                        <p>Price for horoscope</p>
                    </div>

                </div>

            </div>

        </section>

        <!-- about section ends -->

        <!-- skills section starts  -->

        <section class="skills">

            <h1 class="heading"> <span>my</span> skills </h1>

            <div class="box-container">
                <div class="box" v-for="s in skills" :key="s.name">
                    <img :src="s.image">
                    <h3>{{s.name}}</h3>
                </div>

            </div>

        </section>

        <!-- skills section ends -->

        <!-- education section starts  -->

        <section class="education">

            <h1 class="heading"> <span>my</span> experience </h1>

            <div class="box-container">

                <div class="box" v-for="e in experiences" :key="e.years">
                    <div class="box">
                        <i class="fas fa-briefcase"></i>
                        <span>{{e.years}}</span>
                        <h3>{{e.company}}</h3>
                        <p>{{e.jobs}}</p>
                    </div>
                </div>

            </div>

        </section>
    </div>
</template>

<script>
import Navbar from '../components/Navbar.vue'
import axios from "axios"
export default {
    components: { Navbar },
    methods: {
        async fetchExperince() {
            try {
                let res = await axios.get("https://633fc566e44b83bc73c0f545.mockapi.io/profile/v1/experiences")
                this.experiences = res.data
            } catch (error) {
            }
        },
        async fetchSkill() {
            try {
                let res = await axios.get("https://633fc566e44b83bc73c0f545.mockapi.io/profile/v1/skills")
                this.skills = res.data
            } catch (error) {

            }
        }

    },
    data() {
        return {
            name: "Panisara Hangwongngam",
            age: "20",
            email: "panisara.hang@bumail.net" ,
            address: "Nontaburi, Thailand 11110",
            freelance: "make chicken breast and fried egg",
            skill: "Horoscope",
            experience: "2 months",
            language: "English and Thai",
            experiences: [],
            skills: [],
        }
    },
    beforeMount() {
        this.fetchExperince()
        this.fetchSkill()
    }

}
</script>

<style>

</style>