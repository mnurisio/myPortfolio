
<script setup>
import { ref, onMounted } from 'vue';
import profilePic from '../assets/img/profilePic.jpg'

const navLinks = ref(null);

onMounted(() => {
  navLinks.value = document.querySelector('.nav-links');
});

function toggleMenu() {
  if (navLinks.value) {
    navLinks.value.classList.toggle('active');
  }
}

function scrollToSection(id){
  const sectionElem = document.getElementById(id)
  if(sectionElem){
    sectionElem.scrollIntoView({behavior: "smooth"})
  }
}



</script>


<template>
  <header class="header">
    <a href="#" class="logo"><span>Mike Nurisio</span></a>

    <ul class="nav-links">
      <li>
        <a @click.prevent="scrollToSection('about')" href="#about">About</a>
      </li>
      <li>
        <a @click.prevent="scrollToSection('experience')" href="#experience">Experience</a>
      </li>
      <li>
        <a @click.prevent="scrollToSection('projects')" href="#projects">Projects</a>
      </li>
    </ul>

      <i @click.prevent="toggleMenu()" class="mdi mdi-menu menu" id="menu"></i>
    <button class="visit-btn"><a href="https://github.com/mnurisio">Visit Github</a></button>
  </header>

  <section id="about" class="about">
    <div class="about-container">
      <img :src="profilePic" alt="">
      <div class="info-box">
        <div class="text">
          <h3>Hi, I'm</h3>
          <h1>Mike Nurisio</h1>
          <span>Fullstack Developer</span>
        </div>
        <div class="socials">
          <a href="https://github.com/mnurisio"><i class="mdi mdi-github about-icon"></i></a>
          <a href="https://linkedin.com/in/michael-nurisio"><i class="mdi mdi-linkedin about-icon"></i></a>
        </div>
      </div>
    </div>
  </section>

  <section id="experience" class="experience">
    <h2 class="section-title">Experience</h2>
    <div class="experience-info">
      <div class="grid row">
        <div class="grid-card">
          
          <span>Boise CodeWorks</span>
          <h3>Software Developer</h3>
          <p>Went through 500+ of development training where I coded many applications using various backend and frontend technologies.</p>
        </div>
        <div class="grid-card">
          
          <span>Languages, Frameworks, & Databases</span>
          <div class="container-fluid">
            <div class="row">
              <div class="col-md-6">
              <h4>Frontend Development</h4>
              <div class="row">
                <div class="col-md-6">
                    <ul class="language-list">
                      <li>Vue.js</li>
                      <li>HTML</li>
                    </ul>
                </div>
                <div class="col-md-6">
                  <ul class="language-list">
                    <li>CSS</li>
                    <li>JavaScript</li>
                  </ul>
                </div>
              </div>
            </div>
            <div class="col-md-6">
                <h4>Backend Development</h4>
                <div class="row">
                <div class="col-md-6">
                    <ul class="language-list">
                      <li>C#</li>
                      <li>MySQL</li>
                    </ul>
                  </div>
                  <div class="col-md-6">
                    <ul class="language-list">
                      <li>Node.js/Express.js</li>
                      <li>MongoDB</li>
                  </ul>
                </div>
              </div>
              </div>
            </div>
          </div>
        </div>
        <div class="grid-card">
          
          <span>Education</span>
          <h6 class="mt-1">Boise State University: Business Administration - Finance</h6>
          <h6 class="mt-3">Boise CodeWorks:  Certified Fullstack Software Developer</h6>
        </div>
      </div>
    </div>
  </section>


  <section id="projects" class="projects">
    <h2 class="section-title">Projects</h2>

    <div class="projects-grid">

      
      <div class="project-card">
        <h3>Keepr</h3>
        <p>Keepr is a fun and easy-to-use app that helps you organize and store your favorite photos. You can create personalized collections, called "Vaults," and add your pictures, or "Keeps," to them. Whether it's for memories, inspiration, or any other collection, Keepr makes it simple to organize your images and keep them all in one place. With an intuitive design, managing your photo collection has never been easier.</p>
        <div class="btn-group">
          <a class="btn-project" href="https://hello.mnkeepr.com/#/"><div>Live Demo</div></a>
          <a href="https://github.com/mnurisio/Keepr"><div class="btn-project">Github Repo</div></a>
        </div>
      </div>


      <div class="project-card">
        <h3>Tower</h3>
        <p>Tower is a ticketing app that makes discovering and attending social events easy. Users can explore a wide range of events, purchase tickets, and secure their spot with just a few taps. Whether you're looking to attend concerts, parties, or festivals, Tower connects you with the events that match your interests. You can also create and promote your own events, making it a complete platform for event-goers and organizers alike.</p>
        <div class="btn-group">
          <a class="btn-project" href="https://tower.mnkeepr.com/#/"><div>Live Demo</div></a>
          <a href="https://github.com/mnurisio/Tower">
          <div class="btn-project">
              Github Repo
            </div>
          </a>
        </div>
      </div>

      <div class="project-card">
        <h3>Allspice</h3>
        <p>Allspice is an app that brings your culinary creativity to life. It allows users to create, store, and share recipes with a global community. With an easy-to-use interface, you can add all the details of your recipes, from ingredients to photos, and inspire others to try new dishes. Whether you're sharing family favorites or unique creations, Allspice makes it simple to connect with fellow food lovers and share your passion for cooking.</p>
        <div class="btn-group">
          <a class="btn-project" href="https://allspice.mnkeepr.com/#/"><div>Live Demo</div></a>
          <a href="https://github.com/mnurisio/Allspice">
          <div class="btn-project">
              Github Repo
            </div>
          </a>
        </div>
      </div>


    </div>
  </section>

  <footer>

    <ul>
      <li>
        <a @click.prevent="scrollToSection('about')" href="#about">About</a>
      </li>
      <li>
        <a @click.prevent="scrollToSection('experience')" href="#experience">Experience</a>
      </li>
      <li>
        <a @click.prevent="scrollToSection('projects')" href="#projects">Projects</a>
      </li>
    </ul>
  </footer>
</template>


<style lang="scss" scoped>

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Poppins';
  text-decoration: none;
  scroll-behavior: smooth;
  list-style: none;
}

.btn-group{
  display: flex;
  gap: 1rem;
}

.btn-project{
  border-radius: 3rem;
  padding: 0.5rem 1.5rem;
  border: 2px solid black;
  cursor: pointer;
  font-weight: 500;
  text-wrap: nowrap;
  transition: 0.2s ease-in-out;
  color: black;
}

.btn-project a{
  color: black;
}

header{
  position: fixed;
  top: 1rem;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 5rem;
  background-color: rgba(0, 0, 0, 0.8);
  backdrop-filter: blur(8px);
  color: white;
  padding: 0.5rem 1.5rem;
  border-radius: 3rem;
  z-index: 1000;
}

.logo{
  color: white;
  font-size: 1.3rem;
  font-weight: 600;
  text-wrap: nowrap;
  transition: 0.3s ease-in-out;
}

.logo:hover{
  transform: scale(1.1)
}

.nav-links{
  display: flex;
  gap: 2rem;
}

li a{
  position: relative;
  color: white;
  font-weight: 300;
}

li a::before{
  position: absolute;
  content: '';
  width: 0;
  left: 0;
  height: 5px;
  top: 25px;
  border-radius: 1rem;
  transition: 0.3s ease-in-out;
  background: linear-gradient(to right, rgb(46, 204, 113), rgb(108, 92, 231))
}

li a:hover::before{
  width: 100%
}

.visit-btn{
  padding: 0.8rem 1.5rem;
  border-radius: 3rem;
  border: none;
  font-weight: 500;
  font-size: 1rem;
  color: white;
  cursor: pointer;
  text-wrap: nowrap;
  transition: 0.3s ease-in-out;
  background: linear-gradient(to right, rgb(46, 204, 113), rgb(108, 92, 231))
}

.visit-btn a{
  color: white !important;
}

.visit-btn:hover{
  transform: scale(1.03);
  background: linear-gradient(to right, rgb(46, 204, 113), rgb(108, 92, 231))
}

.menu{
  font-size: 2rem;
  display: none;
}

section{
  min-height: 100dvh;
  padding: 8rem 10%;
  width: 100%;
  position: relative;
}

.about{
  display: flex;
  align-items: center;
  justify-content: center;
}

.about-container{
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10rem;
}

.about img{
  object-fit: cover;
  object-position:center;
  height: 45dvh;
  width: 20dvw;
  aspect-ratio: 1/1;
  border-radius: 50%
}

.info-box{
  display: flex;
  flex-direction: column;
  text-align: center;
  align-items: center;
  justify-content: center;
}

.info-box h3{
  font-size: 1.8rem;
  font-weight: 500;
  opacity: 0.8;
}

.info-box h1{
  font-size: 4rem;
  font-weight: 600;
}

.info-box span{
  background: linear-gradient(to right, rgb(46, 204, 113), rgb(108, 92, 231));
  background-clip: text;
  color: transparent;
  font-size: 2rem;
}

.socials{
  display: flex;
  gap: 2rem;
}

.about-icon{
  color: rgba(0, 0, 0, 0.8) !important
}

.socials a{
  font-size: 2.5rem;
  cursor: pointer;
  transition: 0.2s ease-in-out;
}

.socials a:hover{
  transform: scale(1.1)
}


.experience-info{
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 5rem
}

.experience img{
  width: 24vw;
  border-radius: 3rem;
}

.grid{
  // display: flex;
  // grid-template-columns: repeat(2, 1fr);
  gap: 2rem;
}

.grid-card{
  border: 2px solid black;
  border-radius: 3rem;
  padding: 3rem;
  display: flex;
  flex-direction: column;
  align-items: baseline;
  justify-content: left;
  cursor: pointer;
  transition: 0.2s ease-in-out;
}

.grid-card:hover{
  transform: scale(1.02);
  background-color: black;
  color: white;
}

.grid-card span{
  font-size: 1.5rem;
  font-weight: 500;
  background: linear-gradient(to right, rgb(46, 204, 113), rgb(108, 92, 231));
  background-clip: text;
  color: transparent;
}

.language-list{
  padding: 0.5rem;
  padding-left: 0.25rem;
}

.language-list li{
  margin-top: 0.25rem;
}

.projects-grid{
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.project-card{
  padding: 3rem 2rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  gap: 1.5rem;
  border: 2px solid black;
  border-radius: 3rem;
  cursor: pointer;
  transition: 0.3s ease-in-out;
}

.project-card:hover{
  background-color: black;
  color: white;
  transform: translateY(-10px)scale(1.02);
}

.project-card img{
  width: 20vw;
  border-radius: 1rem;
}

.project-card:hover .btn-project{
  border: 2px solid white;
  color: white;
}

.project-card:hover .btn-project a{
  color: white;
}

.project-card:hover .btn-project:hover a{
  color: black;
}

.project-card:hover .btn-project:hover{
  border: 2px solid white;
  background-color: white;
  color: black;
}

.project-card h3{
  font-size: 2rem;
  font-weight: 500
}

footer{
  bottom: 0;
  left: 0;
  height: 10rem;
  width: 100%;
  display: flex;
  flex-direction: column;
  gap: 1rem;
  align-items: center;
  justify-content: center;
}

footer ul{
  display: flex;
  align-items: center;
  gap: 3rem;
}

footer ul li a{
  color: black;
  font-weight: 600;
}

.section-title{
  text-align: center;
  font-size: 4rem;
  font-weight: 600;
  margin-bottom: 3rem;
}

@media(max-width: 1280px){
  header{
    padding: 1rem 2rem;
    gap: 2rem;
  }

  .about .about-container{
    gap: 3rem;
  }

  .experience-info{
    flex-direction: column;
  }



.btn-group{
  display: flex;
  gap: 1rem;
}

}

@media(max-width: 768px){

  .btn-group{
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
  header{
    gap: 1rem;
    padding: 1rem 1rem;
  }

  header .logo{
    font-size: 1rem;
  }

  header .visit-btn{
    display: none;
  }

  .about-container{
    flex-direction: column;
  }

  .grid{
    grid-template-columns: repeat(1, 1fr);
  }

  .experience-info img{
    width: 70vw
  }

 
}

@media(max-width: 600px){

  .btn-group{
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
  header .menu{
    display: block;
  }

  .nav-links{
    position: absolute;
    top: 100%;
    margin-top: 1rem;
    width: 100%;
    padding: 1rem;
    color: white;
    display: flex;
    flex-direction: column;
    text-align: center;
    background: rgba(0, 0, 0, 0.9);
    border-radius: 3rem;
    display: none;
  }

  .nav-links li{
    margin-top: 1.5rem;
    padding: 1rem;
  }

  .nav-links.active{
    display: block;
  }

  header{
    padding: 1rem 2rem;
    gap: 8rem;
  }

  header .logo{
    font-size: 1.5rem;
  }

  .about-container img{
    width: 80vw;
  }

  footer ul{
    gap: 1rem;
  }

  .section-title{
  text-align: center;
  font-size: 3rem;
  font-weight: 600;
  margin-bottom: 3rem;
}
}

</style>
