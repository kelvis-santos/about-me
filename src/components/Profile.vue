<script setup>
import { useMotion } from "@vueuse/motion";
import { onMounted, ref } from "vue";
const div_block = ref();

defineProps({
  msg: String,
  dados: Object | Array,
});

function openCity(cityName) {
  var i, tabcontent, tablinks;
  tabcontent = document.getElementsByClassName("tabcontent");
  for (i = 0; i < tabcontent.length; i++) {
    tabcontent[i].style.display = "none";
  }
  tablinks = document.getElementsByClassName("tablinks");
  for (i = 0; i < tablinks.length; i++) {
    tablinks[i].className = tablinks[i].className.replace(" active", "");
  }
  const citySelected = document.getElementById(cityName);
  citySelected.style.display = "block";
  citySelected.className += " active";
}

onMounted(() => {
  window.onscroll = function () {
    var header = document.getElementById("myHeader");
    var sticky = header.offsetTop;
    if (window.pageYOffset > sticky) {
      header.classList.add("sticky");
    } else {
      header.classList.remove("sticky");
    }
  };
  // Get the element with id="defaultOpen" and click on it
  document.getElementById("defaultOpen").click();
});

useMotion(div_block, {
  initial: {
    opacity: 0,
    y: 500,
  },
  visible: {
    opacity: 1,
    y: 0,
  },
});
</script>

<template>
  <header class="header_main" id="myHeader">
    <!-- <img class="image_profile" alt="Vue logo" :src="dados.foto" /> -->
    <h1 class="header_h1_title">KS</h1>
    <ul class="list_menu">
      <li class="list_item">Skills</li>
      <li class="list_item">Experience</li>
      <li class="list_item">Projects</li>
      <li class="list_item">Contact</li>
    </ul>
  </header>
  <h1 class="header_h1_title">{{ msg }}</h1>
  <nav></nav>
  <!-- img apresentacao -->
  <section class="main_content">
    <div class="main_content_block_intro">
      <div
        class="div_block logo_block"
        v-motion
        :initial="{
          opacity: 0,
          y: 100,
        }"
        :enter="{
          opacity: 1,
          y: 0,
        }"
      >
        <img
          class="main_content_image_profile"
          alt="Kelvis Santos"
          src="../assets/img/me.png"
        />
      </div>
      <div class="div_block_title">
        <div
          class="div_block"
          v-motion
          :initial="{
            opacity: 0,
            y: 100,
          }"
          :enter="{
            opacity: 1,
            y: 0,
          }"
        >
          <p class="text_description">
            Desenvolvedor Full Stack Pleno, sempre buscando por aprimorar minhas
            skills e aprender coisas novas e criar soluções. Experiência com
            todas as etapas do ciclo de desenvolvimento para projetos da decisão
            da interface, desenvolvimento do código a estrutura do banco.
            Conhecimento em diversas linguagens de programação, incluindo
            <b class="text_description_maked">PHP</b>,
            <b class="text_description_maked">JavaScript</b>,
            <b class="text_description_maked">SQL</b>, marcação com
            <b class="text_description_maked">CSS</b>,
            <b class="text_description_maked">HTML5</b>, também na utilização de
            <b class="text_description_maked">APIs</b>, versionamento de código
            com <b class="text_description_maked">GIT</b>, um básico de
            <b class="text_description_maked">Docker</b>,
            <b class="text_description_maked">Linux</b> e Framework
            <b class="text_description_maked">Laravel</b>,
            <b class="text_description_maked">Bootstrap</b>.
          </p>
        </div>
      </div>
    </div>
  </section>
  <!-- SKILLS -->
  <section class="main_content">
    <div class="main_content_block">
      <h1 class="header_skills_title header_h1_title">SKILLS</h1>
      <div class="main_content_row_block">
        <div class="tab">
          <button class="tablinks" @click="openCity('PHP')" id="defaultOpen">
            PHP
          </button>
          <button class="tablinks" @click="openCity('JavaScript')">
            JavaScript
          </button>
          <button class="tablinks" @click="openCity('NodeJS')">NodeJS</button>

          <button class="tablinks" @click="openCity('NodeJS')">NodeJS</button>
          <button class="tablinks" @click="openCity('NodeJS')">NodeJS</button>
          <button class="tablinks" @click="openCity('NodeJS')">NodeJS</button>
          <button class="tablinks" @click="openCity('NodeJS')">NodeJS</button>
          <button class="tablinks" @click="openCity('NodeJS')">NodeJS</button>
          <button class="tablinks" @click="openCity('NodeJS')">NodeJS</button>
        </div>

        <div id="PHP" class="tabcontent">
          <h3 class="about_skill">PHP</h3>
          <p class="about-me-description">
            It is a long established fact that a reader will be distracted by
            the readable content of a page when looking at its layout. The point
            of using Lorem Ipsum is that it has a more-or-less normal
            distribution of letters, as opposed to using 'Content here, content
            here', making it look like readable English. Many desktop publishing
            packages and web page editors now use Lorem Ipsum as their default
            model text, and a search for 'lorem ipsum' will uncover many web
            sites still in their infancy.
          </p>
        </div>

        <div id="JavaScript" class="tabcontent">
          <h3 class="about_skill">JavaScript</h3>
          <p>
            There are many variations of passages of Lorem Ipsum available, but
            the majority have suffered alteration in some form, by injected
            humour, or randomised words which don't look even slightly
            believable. If you are going to use a passage of Lorem Ipsum, you
            need to be sure there isn't anything embarrassing hidden in the
            middle of text.
          </p>
        </div>

        <div id="NodeJS" class="tabcontent">
          <h3 class="about_skill">NodeJS</h3>
          <p>
            Lorem Ipsum has been the industry's standard dummy text ever since
            the 1500s, when an unknown printer took a galley of type and
            scrambled it to make a type specimen book. It has survived not only
            five centuries, but also the leap into electronic typesetting,
            remaining essentially unchanged.
          </p>
        </div>
      </div>
    </div>
  </section>
  <!-- EXPERIENCIA -->
  <section class="main_content">
    <div class="main_content_experience_block">
      <h1 class="header_skills_title header_h1_title">Experiences</h1>
      <div class="main_content_row_block">
        <div class="experience_block">
          <div
            class="content_block_logo_experience"
            v-motion
            :initial="{
              opacity: 0,
              y: 100,
            }"
            :enter="{
              opacity: 1,
              y: 0,
            }"
          >
            <div class="image_experience_block">
              <img
                class="content_block_logo_experience_image flj_logo"
                alt="Logo Grupo FLJ"
                src="../assets/img/logo_flj.png"
              />
            </div>
            <p class="text_experience_description">
              Sed ut perspiciatis unde omnis iste natus error sit voluptatem
              accusantium doloremque laudantium, totam rem aperiam, eaque ipsa
              quae ab illo inventore veritatis et quasi architecto beatae vitae
              dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit
              aspernatur aut odit aut fugit, sed quia consequuntur magni dolores
              eos qui ratione voluptatem sequi nesciunt. Perspiciatis unde omnis
              iste natus error sit voluptatem accusantium doloremque laudantium,
              totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et
              quasi architecto beatae vitae dicta sunt explicabo. Nemo enim
              ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit
            </p>
          </div>
        </div>
        <div class="experience_block">
          <div
            class="content_block_logo_experience"
            v-motion
            :initial="{
              opacity: 0,
              y: 100,
            }"
            :enter="{
              opacity: 1,
              y: 0,
            }"
          >
            <div class="image_experience_block">
              <img
                class="content_block_logo_experience_image made4it_logo"
                alt="Logo Made4it"
                src="../assets/img/logo-made4it.png"
              />
            </div>
            <p class="text_experience_description">
              Sed ut perspiciatis unde omnis iste natus error sit voluptatem
              accusantium doloremque laudantium, totam rem aperiam, eaque ipsa
              quae ab illo inventore veritatis et quasi architecto beatae vitae
              dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit
              aspernatur aut odit aut fugit, sed quia consequuntur magni dolores
              eos qui ratione voluptatem sequi nesciunt. Perspiciatis unde omnis
              iste natus error sit voluptatem accusantium doloremque laudantium,
              totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et
              quasi architecto beatae vitae dicta sunt explicabo. Nemo enim
              ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit
            </p>
          </div>
        </div>
        <div class="experience_block">
          <div
            class="content_block_logo_experience"
            v-motion
            :initial="{
              opacity: 0,
              y: 100,
            }"
            :enter="{
              opacity: 1,
              y: 0,
            }"
          >
            <div class="image_experience_block">
              <img
                class="content_block_logo_experience_image rentcars_logo"
                alt="Logo Rentcars"
                src="../assets/img/rentcars.svg"
              />
            </div>
            <p class="text_experience_description">
              Sed ut perspiciatis unde omnis iste natus error sit voluptatem
              accusantium doloremque laudantium, totam rem aperiam, eaque ipsa
              quae ab illo inventore veritatis et quasi architecto beatae vitae
              dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit
              aspernatur aut odit aut fugit, sed quia consequuntur magni dolores
              eos qui ratione voluptatem sequi nesciunt. Perspiciatis unde omnis
              iste natus error sit voluptatem accusantium doloremque laudantium,
              totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et
              quasi architecto beatae vitae dicta sunt explicabo. Nemo enim
              ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>
  <!-- CONTATO -->
  <section class="main_content">
    <div class="main_content_experience_block">
      <h1 class="header_skills_title header_h1_title">Find me on my networks!</h1>
      <div class="main_content_row_block">
        <!-- <div class="icon-box"> -->
          <div class="social_icon">
            <img class="icon" src="../assets/img/github.png"/>
          </div>
          <div class="social_icon">
            <img class="icon" src="../assets/img/github.png"/>
          </div>
          <div class="social_icon">
            <img class="icon" src="../assets/img/github.png"/>
          </div>
          <div class="social_icon">
            <img class="icon" src="../assets/img/github.png"/>
          </div>
        <!-- </div> -->
      </div>
    </div>
  </section>

  <footer></footer>
</template>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Fira+Sans&family=Tomorrow:ital@1&display=swap");

body {
  overflow-y: hidden; /* Hide vertical scrollbar */
  overflow-x: hidden; /* Hide horizontal scrollbar */
}

section {
  margin: 2rem;
}

.sticky {
  position: fixed;
  /* margin-top: 4%; */
  width: 98.7%;
  z-index: 1;

  /* From https://css.glass */
  background: rgba(51, 71, 86, 0.53) !important;
  border-radius: 16px;
  box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
  backdrop-filter: blur(9.5px);
  -webkit-backdrop-filter: blur(9.5px);
}

.header_main {
  margin-top: -4.6%;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  background-color: rgb(51, 71, 86);
  border-radius: 5px;
  border-bottom: 2px solid #ff4c29;
}

.list_menu {
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  align-items: center;
  list-style: none;
  padding: 0;
  margin: 0;
}

.list_item {
  font-size: 1.8vh;
  text-decoration: none;
  padding: 0.5rem;
  margin: 0.3rem;
  border-radius: 5px;
  font-family: "Fira Sans", sans-serif;
  color: #eeeeee;
  margin-left: 1rem;
}

.list_item:hover {
  border-bottom: 2px solid #ff4c29;
}

.image_profile {
  width: 70px;
  height: 70px;
  border-radius: 50%;
  margin: 0.5rem;
}

a {
  color: #ff4c29;
}

/* Section and div styles */
.main_content {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  /* background-color: aliceblue; */
}

.main_content_block_intro {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100%;
  /* background-color: steelblue; */
}

.main_content_block {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100%;
  /* background-color: steelblue; */
}

.main_content_experience_block {
  display: flex;
  flex-direction: column;
  justify-content: center;
  /* align-items: center; */
  width: 100%;
  height: 371px;
  /* background-color: #2c394b; */
}

.div_block {
  width: 100%;
  height: 250px;
  /* background-color: #ff4c29; */
  border-radius: 5px;
  margin: 0.5rem;
  padding: 0.5rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.div_block_image_dev {
  /* width: 100%; */
  height: 100%;
}

.logo_block {
  width: 30%;
  height: 200px;
  justify-content: end;
}

.content_block_logo_experience {
  padding: 0.5rem;
  /* width: 50%; */
  /* height: 100px; */
  /* display: flex; */
  justify-content: center;
  align-items: center;
}

.div_block_title {
  display: flex;
  margin: 0.5rem;
  width: 50%;
  height: 50%;
  border-radius: 5px;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  padding: 0.5rem;
}

.main_content_image_profile {
  border-radius: 50%;
  width: 220px;
  height: 200px;
  border: 2px solid #ff4c29;
}

.text_description {
  font-family: "Fira Sans", sans-serif;
  font-size: 2vh;
  margin: 0.5rem;
  color: #eeeeee;
}
.text_description_maked {
  color: #ff4c29;
}

.header_h1_title {
  font-family: "Tomorrow", sans-serif;
  font-size: 4vh;
  margin: 0.5rem;
  color: #eeeeee;
  border-bottom: 2px solid #ff4c29;
}

.header_skills_title {
  font-family: "Tomorrow", sans-serif;
  color: #eeeeee;
  width: 100%;
}

.main_content_row_block {
  display: flex;
  flex-direction: row !important;
  justify-content: center;
  align-items: center;
  width: 100%;
  /* height: 100%; */
}

/* Style the tab */
.tab {
  /* float: left; */
  width: 30%;
  height: 300px;
  /* display: flex; */
  flex-direction: column;
  /* background: chartreuse; */
  align-items: center;
  justify-content: center;
  overflow: scroll;
  /* overflow: hidden; */
  overflow-x: hidden;
  margin: 0.5rem;
}

/* width */
::-webkit-scrollbar {
  width: 5px;
}

/* Track */
::-webkit-scrollbar-track {
  box-shadow: inset 0 0 5px 334756;
}

/* Handle */
::-webkit-scrollbar-thumb {
  background: #ff4c29;
  border-radius: 10px;
}

/* Handle on hover */
::-webkit-scrollbar-thumb:hover {
  background: cyan;
}

/* Style the buttons inside the tab */
.tab button {
  /* display: block; */
  font-family: "Tomorrow", sans-serif;
  background-color: inherit;
  color: #ff4c29;
  padding: 15px 16px;
  width: 50%;
  border: none;
  outline: none;
  /* text-align: left; */
  cursor: pointer;
  transition: 0.3s;
  font-size: 14px;
  border: #2c394b 0.1px solid;
  border-radius: 5px;
  margin: 0.1rem;
}
p {
  font-family: "Fira Sans", sans-serif;
  color: #eeeeee;
}

/* Change background color of buttons on hover */
.tab button:hover {
  font-family: "Tomorrow", sans-serif;
  color: cyan;
  border-radius: 0px;
  background: #082032;
  box-shadow: -37px -37px 74px #061927, 37px 37px 74px #0a273d;
  margin: 4px;
  transform: scale(1.1);
  /* color: #4ECCA3; */
}

/* Create an active/current "tab button" class */
.tab button.active {
  /* From https://css.glass */
  font-family: "Tomorrow", sans-serif;
  color: cyan;
  background: #ff4c29;
}

.active {
  font-family: "Tomorrow", sans-serif;
}

/* Style the tab content */
.tabcontent {
  float: left;
  padding: 0px 12px;
  width: 50%;
  border-left: none;
  height: 220px;
}

.about_skill {
  font-family: "Tomorrow", sans-serif;
  color: cyan;
}

.image_experience_block {
  /* width: 100%;
  height: 100%; */
  background-color: #eeeeee;
  width: 100%;
  height: 70px;
  justify-self: center;
  align-items: center;
}
.content_block_logo_experience_image {
  /* width: 100%; */
  /* z-index: -1; */
}

.experience_block {
  /* display: flex;
  flex-direction: row;
  height: 100%; */
  display: flex;
  /* align-items: center; */
  justify-content: center;
  /* width: 25%; */
  margin: 0.2rem;
  font-size: 1.5vh;
}

.made4it_logo {
  margin-top: 0.8rem;
  height: auto;
}

.flj_logo {
  height: 70px;
}

.rentcars_logo {
  margin-top: 0.8rem;
  height: 40px;
}

.about-me-description {
  font-size: 2.1vh;
  color: #eeeeee;
  margin: 0.5rem;
}

@media (max-width: 766px) {
  .main_content_row_block {
    flex-wrap: wrap;
  }
}

.icon-box {
  justify-content: center;
}

.social_icon {
  margin: 2rem;
  background-color: #eeeeee;
  border-radius: 50%;
  /* width: 100%;
  height: 100%; */
}

.icon {
  width: 120px;
  height: 120px;
  margin: 0.5rem;
}
</style>