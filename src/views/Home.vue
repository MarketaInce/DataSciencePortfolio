<template>
  <section id="about-section">
    <div id="about-hero" class="hero container">
      <div class="hero-content">
        <div class="nav-bar-spacer"></div>
        <header id="about-section-content" class="container section-content">
          <h1>Markéta Ince</h1>
          <div class="about">
            <div class="home-information">
              <div class="about-skills text general-card">
                <h2>Hey I'm Markéta</h2>
                <p class="about-intro">I'm a Data Scientist with more than two years of working experience. My language of choice is Python, but I have experience with SQL, R, GNU Octave. I have analytical mindset with strong  attention to detail and a great passion for programming. In the recent year, I started working on front end development to develop user Interfaces to visualize data with JavaScript/ Vue.js.
                </p>
                <div class="skill-box">
                  <div class="skills" v-for="skill in skills" :key="skill.skill">
                    <div class="skill-logo" :style="{ 'background-image': 'url(' + skill.logo + ')' }"></div>
                  </div>
                </div>
              </div>
            </div>
            <figure  class="home-information-picture">
              <img src="/img/Me_01.jpg" alt="Photo of Markéta Ince">
            </figure>
          </div>
        </header>
        <section id="contact-section-content" class="container about-section">
          <h1>Get in Touch</h1>
          <div class="separation-line"></div>
          <p>You can use the links below to contact me and/or see more details.</p>
          <div class="media">
            <div class="contact-row">
              <a class="contact-info" href="/img/CV_Marketa_Ince.pdf" download aria-label="Link to download Markéta Ince's CV.">
                <div class="contact-information-icon">
                  <i class="fas fa-file-download" aria-hidden="true"></i>
                </div>
                <div>Download my CV</div>
              </a>
              <div class="dot"></div>
              <a class="contact-info" href="https://www.linkedin.com/in/marketaince" target="_blank" aria-label="Link to Markéta Ince's LinkedIn Profile.">
                <div class="contact-information-icon">
                  <i class="fab fa-linkedin-in" aria-hidden="true"></i>
                </div>
                <span>linkedin.com/in/marketaince</span>
              </a>
              <div class="dot"></div>
              <a class="contact-info" href="https://github.com/MarketaInce" target="_blank" aria-label="Link to Markéta Ince's GitHub repository.">
                <div class="contact-information-icon">
                  <i class="fab fa-github-alt" aria-hidden="true"></i>
                </div>
                <span>github.com/MarketaInce</span>
              </a>
              <div class="dot"></div>
              <a class="contact-info" href="tel:+32485781729" aria-label="Link to dial Markéta Ince's phone number.">
                <div class="contact-information-icon">
                  <i class="fas fa-mobile-alt" aria-hidden="true"></i>
                </div>
                <span>+32 485 78 17 29</span>
              </a>
              <div class="dot"></div>
              <a class="contact-info" href="mailto:marketa.ince@gmail.com?subject=Mail%20From%20Website" aria-label="Link to send e-mail to Markéta Ince">
                <div class="contact-information-icon">
                  <i class="far fa-envelope" aria-hidden="true"></i>
                </div>
                <span>marketa.ince@gmail.com</span>
              </a>
            </div>
          </div>
        </section>
        <section id="timeline-section-content" class="container about-section">
          <h1>Experiences</h1>
          <div class="separation-line"></div>
          <p>Timeline</p>
          <ul class="timeline">
            <li v-for="event in timeline" :key="event.title" class="elements">
              <div class="element">
                <div class="flag-wrapper">
                  <div class="entry-point"></div>
                  <div class="flag">{{ event.institution }}</div>
                </div>
                <div class="time-wrapper"><span class="time">{{ event.title}}  |  {{ event.date }}</span></div>
                <div class="desc general-card">{{ event.description }}</div>
              </div>
            </li>
          </ul>
        </section>
        <section id="certificates-section-content" class="container certificates-section">
          <h1>Certificates</h1>
          <div class="separation-line"></div>
          <div class="certificates">
            <div v-for="certificate in certificates" :key="certificate.name" class="certificate general-card">
              <div class="certificate-title-logo">
                <a class="certificate-title-logo" :href="certificate.url" target="_blank" v-if="certificate.url !== ''">
                  <div class="certificate-logo" :style="{ 'background-image': 'url(' + certificate.logo + ')' }"></div>
                  <h1 class="certificate-title">{{ certificate.name }}</h1>
                </a>
                <div class="certificate-title-logo" v-if="certificate.url === ''">
                  <div class="certificate-logo" :style="{ 'background-image': 'url(' + certificate.logo + ')' }"></div>
                  <h1 class="certificate-title" >{{ certificate.name }}</h1>
                </div>
              </div>
              <p class="certificate-date">{{ certificate.date }}</p>
              <div>
                <p v-for="desc in certificate.description" :key="desc" class="certificate-description">
                  {{ desc }}
                </p>
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

  components: {},
  name: "About.vue",
  data() {
    return {
      timeline: [{
          classes: "",
          institution: "Valion NV",
          title: "Chatbot App",
          date: "Spring 2020",
          description: "I took a part in an internal POC for the development of a Chatbot App. This app is designed to improve the user experience of potential customers, who want to use a Chatbot on their website."
        },
        {
          classes: "",
          institution: "Het Vlaams Energieagentschap - VO",
          title: "Energy Resources Analysis",
          date: "2018 - 2019",
          description: "The goal of this project is to perform a data analysis for VEA and to discover new insights on the current state of Belgian housing based on a data-driven approach."
        },
        {
          classes: "",
          institution: "Het Facilitair Bedrijf - VO",
          title: "Data Pipelines on AWS",
          date: "2018 - 2019",
          description: "I took part in implementing and automating data flows for assets management of Het Facilitair Bedrijf - VO. I built several data pipeline flows which involve getting data from APIs, applying ETL on them and storing them in Amazon RDS databases."
        },
        {
          classes: "",
          institution: "VDAB",
          title: "Data Science & Machine Learning ",
          date: "2018 - 2019",
          description: "During my internship in Innovation Lab of VDAB, I had the chance to take a part in Next Best Steps (Kans op Werk) project, which is a large-scale project developed by a large team of data science/engineering experts."
        },
        {
          classes: "",
          institution: "Bleckmann",
          title: "Work",
          date: "Mar. 2017 - Jul. 2018",
          description: "Inventory of stock in a logistic company targeted on clothing industry."
        },
        {
          classes: "",
          institution: "Brno University of Technology",
          title: "Master Degree in Civil Engineering",
          date: "2013 - 2017",
          description: "In the year of 2017, I obtained a Masters Degree in the field of Water Management and Water Structures at Faculty of Civil Engineering, BUT. When preparing my final thesis “Analysis of flood situation on selected part of river.”"
        },
        {
          classes: "",
          institution: "Brno University of Technology",
          title: "Bachelor Degree in Civil Engineering",
          date: "2009 - 2013",
          description: "In 2013 I successfully obtained my Bachelors Degree at the Faculty of Civil Engineering. During this four years studies I obtained all the extensive theoretical and practical knowledge required for a future Engineer. My thesis “Revitalization of river for fish,” is focused on evaluating a part of river Svitava in therms of its habitability by aquatic animals."
        }
      ],
      certificates: [{
          name: "Deep Learning Nanodegree",
          date: "Udacity, sep. 2019",
          description: [
            "Focus: Deep Learning topics such as Computer Vision",
            "Natural Language Processing (NLP)",
            "Convolutional Neural Networks (CNNs)",
            "Recurrent Neural Networks (RNNs)", "Generative Adversarial Networks (GANs)."
          ],
          url: "https://confirm.udacity.com/3QERAJML",
          logo: "/img/certificates/Udacity_logo.png"
        },
        {
          name: "Machine Learning - Introduction Nanodegree",
          date: "Udacity, aug. 2019",
          description: [
            "Focus: Most fundamental topics of Machine Learning and Artificial Intelligence."
          ],
          url: "https://confirm.udacity.com/EKFP9KA",
          logo: "/img/certificates/Udacity_logo.png"
        },
        {
          name: "Machine Learning By Standford University ",
          date: "Coursera, jul. 2019",
          description: [
            "Focus: Strongly on mathematics and Machine Learning and Deep Learning theory."
          ],
          url: "https://www.coursera.org/account/accomplishments/certificate/GFNZ8WUGHUFT",
          logo: "/img/certificates/Coursera_logo.png"
        },
        {
          name: "The Modern JavaScript Bootcamp ",
          date: "Udemy, jun. 2020",
          description: [
            "Focus: Bootcamp covering all essential topics to build a real-world app with JavaScript - ES6/ES7."
          ],
          url: "https://www.udemy.com/certificate/UC-027ffebd-e406-4575-8f53-507c29ed5633/",
          logo: "/img/certificates/Udemy_logo.png"
        },
        {
          name: "Spark and Python for Big Data with Pyspark ",
          date: "udemy, jan. 2020",
          description: [
            "Focus: PySpark. Course on Machine Learning with Big Data using Pyspark."
          ],
          url: "https://www.udemy.com/certificate/UC-XBK42HU5/",
          logo: "/img/certificates/Udemy_logo.png"
        },
        {
          name: "Analyzing Your Data With Power BI for BI Professionals ",
          date: "u2u training, oct. 2019",
          description: [
            "Focus: Power BI. On-site one week training provided by U2U nv/sa."
          ],
          url: "",
          logo: "/img/certificates/U2U_logo.png"
        },
        {
          name: "DataCamp Online Trainings",
          date: "Datacamp, 2017 - continUous",
          description: [
            "Multiple trainings provided by DataCamp, covering topics such as data manipulation and cleaning, and data analysis with Python."
          ],
          url: "http://datacamp.com/profile/marketaince",
          logo: "/img/certificates/DataCamp_logo.png"
        }
      ],
      skills: [{
          logo: "/img/skills/Python_logo.png",
          skill: "Python"
        },
        {
          logo: "/img/skills/R_logo.png",
          skill: "R"
        },
        {
          logo: "/img/skills/AWS_logo.png",
          skill: "AWS"
        },
        {
          logo: "/img/skills/GitHub_logo.png",
          skill: "GitHub"
        },
        {
          logo: "/img/skills/JavaScript_logo.png",
          skill: "JavaScript/ES6"
        },
        {
          logo: "/img/skills/Vue_js_logo.png",
          skill: "Vue.js"
        },
        {
          logo: "/img/skills/Spark_logo.png",
          skill: "PySpark"
        },
        {
          logo: "/img/skills/PowerBI_logo.png",
          skill: "Power BI"
        }
      ]
    }
  }
}
</script>

<style lang="scss">
@import "./src/scss/_variables.scss";

/* Desktop Settings */

#about-section {
  position: relative;
  text-align: center;
  color: black;
  h1 {
    color: $dark-background;
  }
}

.about-section,
.certificates-section {
  padding-bottom: 2rem;
  margin: 0 auto;
  h1 {
    letter-spacing: 0.1em;
    font-size: 2rem;
    padding-top: 0.5rem;
    text-align: center;
    color: $flags-light;
  }
}


/*** ABOUT SECTION CONTENT ***/

#about-section-content {
  h1 {
    margin-top: 2rem;
    color: $dark-background;
    letter-spacing: 0.1em;
    font-size: 4rem;
    font-variant: small-caps;
  }
}

.about {
  margin: 0 3rem 3rem 3rem;
  display: grid;
  grid-gap: 2rem;
  grid-template-columns: 700px 1fr;
  padding: 2rem;
}

.home-information {
  padding: 1rem;
}

.home-information-picture {
  padding: 1rem;
  display: flex;
  img {
    border-radius: 3rem;
    display: block;
    width: 100%;
    box-shadow: 0 1px 5px 1px #7a7777;
    margin: auto;
  }
}

.about-intro {
  margin: 0;
  padding: 0;
  color: black;
}

.about-skills {
  padding: 2rem;
  h2 {
    color: $flags-light;
  }
  &.text {
    height: fit-content;
    color: black;
  }
  .skills {
    margin: auto;
    display: block;
    .skill-logo {
      min-width: 60px;
      width: 60px;
      height: 60px;
      background-size: 60px 60px;
      border-radius: 50%;
      font-weight: bold;
      align-items: center;
      justify-content: center;
      text-align: center;
      user-select: none;
      background-position-x: 0%;
      background-position-y: 0%;
      background-repeat-x: no-repeat;
      background-repeat-y: no-repeat;
      background-attachment: scroll;
      background-origin: content-box;
      background-clip: border-box;
      background-color: white;
    }
  }
}

.skill-box {
  display: grid;
  grid-template-columns: repeat(6, 1fr);
}


/*** CONTACT SECTION CONTENT ***/

.contact-information-icon {
  text-align: center;
  margin: auto 0.5rem auto 0;
  display: inline-block;
  width: 60px;
  i {
    color: $flags;
    font-size: 3.5rem;
    padding-bottom: 0.5rem;
  }
  img {
    max-width: 60px;
  }
}

.dot {
  background-color: $dark-background;
  width: 5px;
  height: 5px;
  border-radius: 50%;
}

.contact-info {
  display: flex;
  flex-direction: column;
  align-items: center;
  transform: translateZ(0);
  transition: transform 750ms cubic-bezier(0.2, 1, 0.3, 1);
  &:hover {
    transform: scale(1.05);
  }
}

.media {
  color: $flags-light;
  margin: 3rem;
  a {
    color: $dark-background;
  }
  .contact-row {
    display: flex;
    justify-content: space-around;
    margin-bottom: 0.5rem;
    align-content: center;
    align-items: center;
  }
}


/*** TIMELINE SECTION CONTENT ***/

// timeline styles
.element {
  float: none;
  width: 100%;
  text-align: center;
}

.flag-wrapper {
  display: block;
  position: relative;
}

.entry-point {
  border: 0;
  float: left;
  text-align: center;
  height: 35px;
  width: 60px;
  font-size: 22px;
  background: $flags;
  color: #000000;
  position: relative;
  margin-top: 15px;
  &:before {
    content: "";
    position: absolute;
    left: 0;
    width: 0;
    height: 0;
    border-bottom: 15px solid $flags;
    border-left: 30px solid transparent;
    border-right: 30px solid transparent;
    top: -15px;
  }
  &:after {
    content: "";
    position: absolute;
    left: 0;
    width: 0;
    height: 0;
    border-left: 30px solid transparent;
    border-right: 30px solid transparent;
    border-top: 15px solid $flags;
    bottom: -15px;
  }
}

.flag {
  position: relative;
  display: inline-block;
  background: $flags;
  font-weight: 600;
  z-index: 15;
  padding: 6px 10px;
  border-radius: 5px;
  color: white;
}

.time-wrapper {
  display: block;
  position: relative;
  line-height: 1em;
  vertical-align: middle;
  color: #000000;
  z-index: 17;
}

.company-wrapper {
  display: block;
  position: relative;
  line-height: 1em;
  vertical-align: middle;
  z-index: 16;
}

.time {
  background: $flags-light;
  display: block;
  padding: 8px;
  color: #fff;
}

.company {
  background: $dark-background;
  display: block;
  padding: 10px 20px;
  color: #fff;
}

.desc {
  position: relative;
  margin: 1.8em 0 0 0;
  padding: 1em;
  color: black;
  z-index: 15;
  border-radius: 20px;
}

.element {
  & .flag:after {
    content: "";
    position: absolute;
    left: 50%;
    height: 0;
    width: 0;
    margin-left: -8px;
    border: 8px solid transparent;
    border-bottom-color: $flags;
    pointer-events: none;
  }
  & .time-wrapper {
    float: none;
  }
  & .company-wrapper {
    float: none;
  }
  & .desc {
    position: relative;
    padding: 1em;
    z-index: 15;
  }
}

.timeline {
  position: relative;
  padding: 0;
  width: 100%;
  margin-top: 3rem;
  list-style-type: none;
  &:before {
    position: absolute;
    left: 50%;
    top: 0;
    content: ' ';
    display: block;
    width: 2px;
    height: 100%;
    margin-left: -1px;
    background: rgb(213, 213, 213);
    background: -moz-linear-gradient(top, rgba(213, 213, 213, 0) 0%, rgb(213, 213, 213) 8%, rgb(213, 213, 213) 92%, rgba(213, 213, 213, 0) 100%);
    background: -webkit-gradient(linear, left top, left bottom, color-stop(0%, rgba(30, 87, 153, 1)), color-stop(100%, rgba(125, 185, 232, 1)));
    background: -webkit-linear-gradient(top, rgba(213, 213, 213, 0) 0%, rgb(213, 213, 213) 8%, rgb(213, 213, 213) 92%, rgba(213, 213, 213, 0) 100%);
    background: -o-linear-gradient(top, rgba(213, 213, 213, 0) 0%, rgb(213, 213, 213) 8%, rgb(213, 213, 213) 92%, rgba(213, 213, 213, 0) 100%);
    background: -ms-linear-gradient(top, rgba(213, 213, 213, 0) 0%, rgb(213, 213, 213) 8%, rgb(213, 213, 213) 92%, rgba(213, 213, 213, 0) 100%);
    background: linear-gradient(to bottom, rgba(213, 213, 213, 0) 0%, rgb(213, 213, 213) 8%, rgb(213, 213, 213) 92%, rgba(213, 213, 213, 0) 100%);
    z-index: 5;
  }
  & .entry-point {
    width: 16px;
    height: 10px;
    position: absolute;
    background: $secondary;
    z-index: 5;
    left: 0;
    right: 0;
    margin-left: auto;
    margin-right: auto;
    top: -30px;
    margin-top: 0;
    &:before {
      border-bottom: 4px solid $secondary;
      border-left-width: 8px;
      border-right-width: 8px;
      top: -4px;
    }
    &:after {
      border-left-width: 8px;
      border-right-width: 8px;
      border-top: 4px solid $secondary;
      bottom: -4px;
    }
  }
  & li {
    padding: 2em 0;
    &:after {
      content: "";
      display: block;
      height: 0;
      clear: both;
      visibility: hidden;
    }
  }
  & li:nth-child(even) .flag-wrapper {
    text-align: left;
  }
  & li:nth-child(odd) .flag-wrapper {
    text-align: right;
  }
  & li:nth-child(odd) .element {
    position: relative;
    width: 631px;
    float: left;
    text-align: right;
  }
  & li:nth-child(even) .element {
    position: relative;
    width: 631px;
    float: right;
    text-align: left;
  }
  & li:nth-child(even) .entry-point {
    left: -28px;
    right: auto;
    top: 14px;
  }
  & li:nth-child(odd) .entry-point {
    left: auto;
    right: -28px;
    top: 14px;
  }
  & li:nth-child(odd) .element .flag {
    text-align: right;
  }
  & li:nth-child(even) .element .flag {
    text-align: left;
  }
  & li:nth-child(odd) .element .flag:after {
    left: auto;
    right: -16px;
    top: 20px;
    margin-top: -8px;
    border: 8px solid transparent;
    border-left-color: $flags;
  }
  & li:nth-child(even) .element .flag:after {
    top: 20px;
    margin-top: -8px;
    border: 8px solid transparent;
    border-right-color: $flags;
    left: -8px;
  }
  & li:nth-child(odd) .element .time-wrapper {
    float: right;
    margin-right: 0.5rem;
    .time {
      border-radius: 5px 0 5px 5px;
    }
  }
  & li:nth-child(even) .element .time-wrapper {
    float: left;
    margin-left: 0.5rem;
    .time {
      border-radius: 0 5px 5px 5px;
    }
  }
  & li:nth-child(odd) .element .company-wrapper {
    float: right;
    margin-right: -0.5rem;
    margin-top: 0.2rem;
    .company {
      border-radius: 5px 0 5px 5px;
      padding-right: 25px;
    }
  }
  & li:nth-child(even) .element .company-wrapper {
    float: left;
    margin-left: -0.5rem;
    margin-top: 0.2rem;
    .company {
      border-radius: 0 5px 5px 5px;
      padding-left: 25px;
    }
  }
}


/*** CERTIFICATES SECTION CONTENT ***/

.certificates {
  margin-top: 3rem;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 2rem;
  border-radius: 2rem;
  a.certificate-title-logo {
    transform: translateZ(0);
    transition: transform 750ms cubic-bezier(0.2, 1, 0.3, 1);
    &:hover {
      transform: scale(1.05);
    }
  }
  .certificate-title-logo {
    display: flex;
    align-items: flex-start;
    float: left;
    .certificate-logo {
      min-width: 50px;
      width: 50px;
      height: 50px;
      background-size: 50px 50px;
      margin: auto 1rem auto 0;
      display: flex;
      border-radius: 50%;
      font-weight: bold;
      align-items: center;
      justify-content: center;
      text-align: center;
      user-select: none;
      background-position-x: 0%;
      background-position-y: 0%;
      background-repeat-x: no-repeat;
      background-repeat-y: no-repeat;
      background-attachment: scroll;
      background-origin: content-box;
      background-clip: border-box;
      background-color: transparent;
    }
  }
}

.certificate {
  display: flex;
  flex-direction: column;
  padding: 2rem;
  & .certificate-title {
    font-size: 0.8rem;
    text-align: left;
    margin: auto 1rem auto 0;
    color: black;
    display: block;
  }
  & .certificate-date {
    font-size: 0.6rem;
    color: $dark-background;
    text-transform: uppercase;
    margin-bottom: 1rem;
    margin-top: 0.5rem;
  }
  & .certificate-description {
    font-size: 0.7rem;
    color: black;
    text-align: justify;
  }
}


/* Desktop Settings <= 1400px */

@media (max-width: 1400px) {
  .home-information-picture {
    img {
      width: 500px;
    }
  }
  .dot {
    display: none;
  }
  .media {
    .contact-row {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
    }
  }
  .timeline {
    width: 800px;
    margin: 20px auto 0;
  }
  .timeline li:nth-child(odd) .element {
    position: relative;
    width: 380px;
    float: left;
    text-align: right;
  }
  .timeline li:nth-child(even) .element {
    position: relative;
    width: 380px;
    float: right;
    text-align: left;
  }
}


/* Tablet Vertical Settings <= 1024px  --- ex. iPad Pro */

@media (max-width: 1024px) {
  .about {
    display: block;
    margin: 0;
  }
  .about-skills {
    margin-bottom: 2rem;
  }
}


/* Tablet Vertical Settings <= 900px */

@media (max-width: 900px) {
  .home-information-picture {
    img {
      width: 400px;
    }
  }
  .media {
    .contact-row {
      grid-template-columns: repeat(2, 1fr);
      padding: 0 3rem;
      grid-gap: 2rem;
    }
  }
  .timeline {
    width: 620px;
    margin: 20px auto 0;
  }
  .timeline li:nth-child(odd) .element {
    position: relative;
    width: 290px;
    float: left;
    text-align: right;
  }
  .timeline li:nth-child(even) .element {
    position: relative;
    width: 290px;
    float: right;
    text-align: left;
  }
}


/* Tablet Vertical Settings <= 768px --- ex. iPad */

@media (max-width: 768px) {
  #about-section-content {
    h1 {
      margin-top: 0;
      font-size: 3rem;
    }
  }
  .certificates {
    grid-template-columns: repeat(2, 1fr);
    .certificate-title-logo {
      .certificate-logo {
        min-width: 50px;
        width: 50px;
        height: 50px;
        background-size: 50px 50px;
      }
    }
  }
}


/* Mobile Horizontal Settings <= 500px --- ex. Pixel 2 */

@media (max-width: 750px) and (max-height: 500px) {}


/* Mobile Horizontal Settings <= 300px --- ex. Galaxy Fold */

@media (max-width: 700px) and (max-height: 300px) {}


/* Mobile Horizontal Settings <= 400px --- ex. iPhone 6 */

@media (max-width: 680px) and (max-height: 400px) {
  .timeline {
    width: 560px;
    margin: 20px auto 0;
  }
  .timeline li:nth-child(odd) .element {
    position: relative;
    width: 260px;
    float: left;
    text-align: right;
  }
  .timeline li:nth-child(even) .element {
    position: relative;
    width: 260px;
    float: right;
    text-align: left;
  }
  .certificates {
    display: block;
    .certificate {
      margin-bottom: 2rem;
    }
  }
}


/* Mobile Vertical Settings <= 500px --- ex. Pixel 2 */

@media (max-width: 500px) {
  .media {
    margin: 3rem 0;
    .contact-row {
      display: block;
      padding: 0 1rem;
      a {
        display: flex;
        align-items: center;
        justify-content: start;
        flex-direction: row;
        margin-bottom: 1rem;
      }
    }
  }
  .contact-information-icon {
    margin-right: 1rem;
    width: 50px;
    img {
      width: 50px;
    }
    i {
      font-size: 3.1rem;
      padding-bottom: 0;
    }
  }
  .skill-box {
    grid-template-columns: repeat(4, 1fr);
  }
  .home-information-picture {
    img {
      width: 250px;
    }
  }
  #about-section {
    &::before {
      height: 8rem;
    }
  }
  .about {
    padding: 0;
  }
  .about-skills {
    .skills {
      .skill-logo {
        min-width: 45px;
        width: 45px;
        height: 45px;
        background-size: 45px 45px;
      }
    }
  }
  .certificates {
    display: block;
    .certificate {
      margin-bottom: 2rem;
      & .certificate-title {
        font-size: 1rem;
      }
    }
    .certificate-title-logo {
      .certificate-logo {
        min-width: 30px;
        width: 30px;
        height: 30px;
        background-size: 30px 30px;
      }
    }
  }
  .certificates-section {
    margin: 2rem 0 0 0;
  }
  .timeline {
    & li:nth-child(even) .element,
    & li:nth-child(odd) .element {
      text-align: left;
      float: left;
      margin-left: 1.2rem;
    }
    & li:nth-child(even) .flag-wrapper,
    & li:nth-child(odd) .flag-wrapper {
      text-align: left;
    }
    & li:nth-child(even) .element .flag,
    & li:nth-child(odd) .element .flag {
      text-align: left;
    }
    & li:nth-child(even) .entry-point,
    & li:nth-child(odd) .entry-point {
      left: -28px;
      right: auto;
    }
    & li:nth-child(odd) .element .flag:after {
      top: 20px;
      margin-top: -8px;
      border: 8px solid transparent;
      border-right-color: $flags;
      left: -8px;
    }
    & li:nth-child(odd) .element .time-wrapper {
      float: left;
      margin-left: 0.5rem;
      .time {
        border-radius: 0 5px 5px 5px;
      }
    }
  }
  .timeline:before {
    position: absolute;
    left: 0;
  }
}


/* Mobile Vertical Settings <= 400px --- ex. iPhone 6 */

@media (max-width: 400px) {
  .container {
    padding: 0 0.5rem;
  }
  .contact-information-icon {
    width: 30px;
    img {
      width: 30px;
    }
    i {
      font-size: 1.8rem;
    }
  }
  .timeline {
    & li:nth-child(even) .element,
    & li:nth-child(odd) .element {
      width: 250px;
    }
  }
}


/* Mobile Vertical Settings <= 300px --- ex. Galaxy Fold */

@media (max-width: 300px) {
  .timeline {
    & li:nth-child(even) .element,
    & li:nth-child(odd) .element {
      width: 200px;
    }
  }
}
</style>