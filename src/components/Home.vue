<template>
  <div
    :class="{ 'bg-white': !nightMode, 'bg-dark': nightMode }"
    class="pt-5 p-st"
  >
    <div
      class="container"
      data-aos="fade"
      data-aos-once="true"
      data-aos-duration="1000"
    >
      <div class="row align-items-center">
        <div class="col-xl-4 col-bg-6 col-md-6 col-sm-12 pb-5 pr-5 text-center">
          <img :src="picture"/>
        </div>
        <div class="col-xl-8 col-bg-6 col-md-6 col-sm-12 pt-5 pl-5">
          <span
            class="home-title"
            :class="{ pgray: !nightMode, 'text-light': nightMode }"
            >Cheers, I am Matias 🙋🏻‍♂️</span
          >
          <div>
            <p>A home-awarded frontend developer from Corrientes <span class="emoji">🧉</span> (Argentina) currently living in the sunny Barcelona <span class="emoji">🌞</span>.
            <br>I've worked with music and different people for many years and that's why now, I choose websites..
            <br>I collaborate with the marketing team of the current company I work for to develop, maintain and anhance a variety of websites in an industrial market and some 
            e-commerces for a wide customer profile while we give them the best web experience.
            <br>Created (and screwed) many start-up companies, lived in more than 6 different cities, speak 5 different languages, played music for many bands, 
            learned how to code after my 30's, travelled by <span class='increase1'>car</span>, <span class='increase2'>bus</span>, <span class='increase3'>at the sit of my lovely bike</span>, 
            <span class='increase4'>backpacked</span>, <span class='increase5'>camped</span>, <span class='increase6'>cooked</span>, <span class='increase7'>hicked</span> and 
            <span class='increase8'>runned</span>.... 
            I guess I like to stay active.
            <br>I have 2 years of experience as a developer and I love playing/working with Javascript and some of its top frameworks to make HTML and CSS alive! <span class="emoji">🧟‍♂️</span></p>
          </div>
          <div class="text-center m-2 pb-4">
            <button
              class="btn btn-outline-secondary mx-2 "
              @click="open('linkedin')"
              v-tooltip.bottom="'LinkedIn'"
            >
              <i class="fab fa-linkedin"></i>
            </button>
            <button
              class="btn btn-outline-secondary mx-2"
              @click="open('github')"
              v-tooltip.bottom="'GitHub'"
            >
              <i class="fab fa-github"></i>
            </button>
            <button
              class="btn btn-outline-secondary mx-2"
              @click="open('resume')"
              v-tooltip.bottom="'Resume'"
            >
              <i class="fa fa-file"></i>
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import info from "../../info";

// import wave from "./helpers/Wave";

export default {
  name: "Home-el",
  components: {
    // Wave,
  },
  props: {
    nightMode: {
      type: Boolean,
    },
  },
  data() {
    return {
      picture: info.flat_picture,
      description: info.description,
      name: info.name,
      linkedin: info.links.linkedin,
      github: info.links.github,
      resume: info.links.resume
    };
  },
  methods: {
    open(link) {
      switch (link) {
        case "linkedin":
          window.open(this.linkedin, "_blank");
          break;
        case "github":
          window.open(this.github, "_blank");
          break;
        case "resume":
          window.open(this.resume, "_blank");
          break;
      }
    },
  },
};
</script>

<style scoped>
.home-title {
  font-size: 32px;
  font-weight: 500;
}

img {
  max-width: 350px;
  max-height: 350px;
  margin-top: 50px;
  margin-bottom: 30px;
  border-radius: 50%;
}

@media only screen and (max-width: 580px) {
  img {
    object-fit: cover;
    border-radius: 50%;
    height: 200px;
    width: 200px;
    margin-bottom: 5px;
    align-self: center;
    border: 2px solid rgb(205, 205, 205);
  }
  p {
    font-weight: 400;
    letter-spacing: inherit;
    font-size: 0.80rem; 
    line-height: 1rem;
  }
  .home-title {
    font-size: 28px;
  }
}

.fa {
  font-size: 15px;
}

.btn {
  border-color: #759CC9;
  color: #759CC9;
}

.btn:hover {
  background-color: #759CC9;
  border-color: #759CC9;
  color: white;
}

.btn:focus {
  background-color: #759CC9;
  border-color: #759CC9;
  color: white;
}

.btn:focus {
  outline: none !important;
}

p {
  text-align: left;
  font-weight: 400;
  letter-spacing: 0.06em;
  line-height: 1.9em;
}

.emoji {
  font-size: 1.4rem;
}

.increase1 {
  font-size: 1.25rem;
  letter-spacing: 0.04em;
}
.increase2 {
  font-size: 1.4rem;
  letter-spacing: 0.04em;
}
.increase3 {
  font-size: 1.48rem;
  letter-spacing: 0.04em;
}
.increase4 {
  font-size: 1.57rem;
  letter-spacing: 0.04em;
}
.increase5 {
  font-size: 1.64rem;
  letter-spacing: 0.04em;
}
.increase6 {
  font-size: 1.71rem;
  letter-spacing: 0.04em;
}
.increase7 {
  font-size: 1.79rem;
  letter-spacing: 0.04em;
}
.increase8 {
  font-size: 1.87rem;
  letter-spacing: 0.04em;
}
/* leaves */
</style>
