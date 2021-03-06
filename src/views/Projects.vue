<template>
  <section id="project-section">
    <div id="project-hero" class="hero container">
      <div class="hero-content">
        <div class="nav-bar-spacer"></div>
        <header id="project-section-content" class="container section-content">
          <h1>My Projects</h1>
          <div class="separation-line"></div>
          <p>Check Some of My Projects Below.</p>
        </header>
        <section class="projects-cards container" >
          <div class="projects">
            <div class="project general-card" v-for="project in projects" :key="project.name">
              <div class="wrapper">
                <div >
                  <h2 class="project-text-title">{{ project.name }}</h2>
                </div>
                <div class="project-image">
                  <img :src="project.background" alt="" />
                </div>
                <div class="project-text">
                  <div class="project-text-wrap">
                    <p class="project-text-category">{{ project.category }}</p>
                    <p class="project-text-description" >{{ project.description | descriptionLimitFilter }}</p>
                    <div class="project-text-buttons">
                      <router-link :to="project.demo_link" v-if="project.demo_link!==''">
                        <i class="fas fa-vial"></i>
                        <p>DEMO</p>
                      </router-link>
                      <a :href="project.blog_link" target="_blank" v-if="project.blog_link!==''">
                        <i class="fas fa-blog"></i>
                        <p>BLOG</p>
                      </a>
                      <a :href="project.github_link" target="_blank" v-if="project.github_link!==''">
                        <i class="fab fa-github-alt"></i>
                        <p>GITHUB</p>
                      </a>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </section>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Projects.vue",
  data() {
    return {
      projects: [{
          name: "Dog App",
          category: "Data Science",
          background: "/img/Dog_App.jpg",
          description: "Simple application to recognize dog breeds using Convolutional Neural Network architecture. This project was a part of Udacity Deep Learning Nanodegree.",
          demo_link: "/projects/dogapp",
          blog_link: "",
          github_link: "https://github.com/MarketaInce/DogAppCNN.git"
        },
        {
          name: "Face Generator",
          category: "Data Science",
          background: "/img/Face_Generator.jpg",
          description: "GAN that is able to generate new human faces, trained on data from celebrities (celebs data). This project was a part of Udacity Deep Learning Nanodegree.",
          demo_link: "",
          blog_link: "",
          github_link: "https://github.com/MarketaInce/FaceGeneratorAppGAN"
        },
        {
          name: "TV Scripts Generator",
          category: "Data Science",
          background: "/img/TV_Scripts_Generator.jpg",
          description: "It is possible to use RNN to generate new original TV scripts. This project was a part of Udacity Deep Learning Nanodegree.",
          demo_link: "",
          blog_link: "",
          github_link: "https://github.com/MarketaInce/GenerateTVScriptsRNN"
        },
        {
          name: "Portfolio",
          category: "Web Development",
          background: "/img/Portfolio.jpg",
          description: "Data Science Portfolio.",
          demo_link: "",
          blog_link: "",
          github_link: "https://github.com/MarketaInce/DataSciencePortfolio"
        },
      ],
    }
  }
}
</script>

<style lang="scss">
/* Import scss variables */

@import "./src/scss/_variables.scss";

/* Desktop Settings */

#project-section {
  position: relative;
}

.projects-cards {
  padding-bottom: 2rem;
  .projects {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-gap: 3rem;
    margin-bottom: 4rem;
    margin-top: 1rem;
    .project {
      position: relative;
      overflow: hidden;
      .wrapper {
        margin: 2rem;
        height: 550px;
        overflow: hidden;
      }
      // Add color overlay
      &::after {
        content: "";
        position: absolute;
        display: block;
        background: $secondary;
        opacity: 0.9;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        transform: scale(2) translateX(0) translateY(100%) rotate(-10deg);
        transition: transform 2s cubic-bezier(0.2, 1, 0.3, 1);
      }
      // Bring in main color overlay
      &:hover:after {
        transform: scale(2) translateX(0) translateY(40%) rotate(-10deg);
      }
      // Scale image on hover
      &:hover .project-image {
        transform: scale(1.05);
      }
      // Bring in text on hover
      &:hover .project-text {
        opacity: 1;
        transform: translateY(0);
      }
      .project-text-title {
        color: black;
        text-align: center;
        margin-bottom: 1rem;
      }
      &-image {
        height: auto;
        transform: translateZ(0);
        display: block;
        transition: transform 750ms cubic-bezier(0.2, 1, 0.3, 1);
      }
      &-image:before {
        content: "";
        display: block;
        padding-top: 75%;
        overflow: hidden;
      }
      &-image img {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: auto;
        line-height: 0;
        overflow: hidden;
      }
      &-text {
        position: absolute;
        left: 0;
        bottom: 0;
        right: 0;
        opacity: 0;
        text-align: center;
        z-index: 1;
        color: #fff;
        transform: translateY(-100%);
        transition: opacity 500ms cubic-bezier(0.2, 1, 0.3, 1), transform 500ms cubic-bezier(0.2, 1, 0.3, 1);
        transition-delay: 300ms;
        p {
          padding: 0 2rem;
          margin: 1rem 0 2rem 0;
        }
      }
      &-text-wrap {
        position: absolute;
        width: 100%;
        bottom: 0;
      }
      &-text-buttons {
        display: flex;
        justify-content: space-around;
        i {
          font-size: 2rem;
          display: block;
          margin: auto auto 0.7rem auto;
        }
        a {
          cursor: pointer;
          margin: 0 auto;
        }
        img {
          width: 40px;
          margin: auto;
        }
        p {
          margin-top: 0;
        }
      }
      &-text-title {
        font-size: 1.8rem;
        padding: 0 1rem;
        margin: 5px 0 0 0;
      }
      &-text-category {
        text-transform: uppercase;
        font-size: 1.2rem;
        opacity: 0.7;
        margin: 0;
      }
    }
  }
}


/* Desktop Settings <= 1400px */

@media (max-width: 1400px) {}


/* Tablet Vertical Settings <= 1024px  --- ex. iPad Pro */

@media (max-width: 1024px) {
  .projects-cards {
    .projects {
      grid-template-columns: repeat(2, 1fr);
    }
  }
}


/* Tablet Vertical Settings <= 900px */

@media (max-width: 900px) {}


/* Tablet Vertical Settings <= 768px --- ex. iPad */

@media (max-width: 768px) {
  .projects-cards {
    .projects {
      margin: 1rem 0 0 0;
      display: block;
      .project {
        margin-bottom: 2rem;
        .wrapper {
          height: 450px;
          h2 {
            font-size: 1.4rem;
          }
        }
        &-text-buttons {
          font-size: 0.8rem;
          img {
            width: 30px;
          }
        }
      }
    }
  }
}


/* Mobile Horizontal Settings <= 500px --- ex. Pixel 2 */

@media (max-width: 750px) and (max-height: 500px) {
  .projects-cards {
    .projects {
      display: block;
      .project {
        margin-bottom: 2rem;
      }
    }
  }
}


/* Mobile Horizontal Settings <= 300px --- ex. Galaxy Fold */

@media (max-width: 700px) and (max-height: 300px) {}


/* Mobile Horizontal Settings <= 400px --- ex. iPhone 6 */

@media (max-width: 680px) and (max-height: 400px) {}


/* Mobile Vertical Settings <= 500px --- ex. Pixel 2 */

@media (max-width: 500px) {
  #project-section {
    &::before {
      height: 8rem;
    }
  }
  .projects-cards {
    .projects {
      //display: block;
      .project {
        margin-bottom: 2rem;
        .wrapper {
          height: 250px;
          h2 {
            font-size: 1.2rem;
          }
        }
        .project-text-category {
          font-size: 1rem;
          margin: 0.5rem 0;
        }
        .project-text-title {
          font-size: 1.5rem;
        }
        .project-text-description {
          font-size: 0.8rem;
          margin: 0.5rem 0;
        }
        .project-text-buttons {}
        &:hover:after {
          transform: scale(2) translateX(0) translateY(30%) rotate(-10deg);
        }
        &-text-buttons {
          padding: 0.1rem 0.1rem;
          justify-content: center;
          img {
            width: 25px;
          }
          p {
            padding: 0;
            margin: 0 0 0.5rem 0;
          }
        }
      }
    }
  }
}


/* Mobile Vertical Settings <= 400px --- ex. iPhone 6 */

@media (max-width: 400px) {
  .projects {
    .project {
      .wrapper {
        margin: 1.5rem;
      }
    }
  }
}


/* Mobile Vertical Settings <= 300px --- ex. Galaxy Fold */

@media (max-width: 300px) {
  .projects {
    .project {
      .wrapper {
        h2 {
          font-size: 1rem;
        }
        margin: 1rem;
      }
    }
  }
}
</style>