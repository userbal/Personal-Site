<template>
  <div id="container" :style="{color: textColor, backgroundColor: backgroundColor}">
    <div>
      <h1>Andrew Lewis</h1>
      <h5>
        Objective:  Continue to and expand programming knowledge and provide meaningful work to the community.
      </h5>
      <div id="main">
        <div id="main-content">
          <div class="section">
            <h3 :style="{color: highlightColor}">Experience</h3>
            <div class="section-body">
              <span class="name">Printerlogic</span>, St. George, UT — Software Engineer Intern
              <div class="date">Feb 2020 - Present</div>
              Vasion Team: Frontend development using Vue.js.
              <div class="date">Aug 2019 - Feb 2020</div>
              Integrations Team: Backend development using Node.js and Amazon Web Services. Responsible for data transfer between teams.
              <br>
            </div>
            <div class="section-body">
              <span class="name">L’Chef</span>, St. George, UT — Online Sales<br>
              <div class="date">July 2018 - Aug 2019</div>
              Primary caretaker of several wordpress websites, including boschmixers.com. Responsibilities included adapting to customer feedback and building an interface that catered to many different demographics. Used Google Analytics, Wordpress and Woocommerce to meet company needs.
            </div>
          </div>
          <div class="section">
            <h3 :style="{color: highlightColor}">Education</h3>
            <div class="section-body">
              <span class="name">Dixie State University</span>, St. George, UT<br>
              <div class="date">Graduated May 2020</div>
              Bachelor of Science in Computer Information Tech - Software Development Emphasis<br>
            </div>
          </div>
          <div class="section">
            <h3 :style="{color: highlightColor}">References</h3>
            <span class="name">Cathy Robertson</span> - L’Chef<br>
            (801) 819-7985
            cathy@lchef.com
            <br><br>
            <span class="name">Tyler Reber</span> — L’Chef<br>
            (801) 209-4535
            samtreber@gmail.com<br>
          </div>
        </div>
        <div id="side-bar">
          <h3 :style="{color: highlightColor}">Contact Info</h3>
          <div id="contact-info">
            422 E Stonehedge Cir
            St. George, UT 84770
            <br>
            <span class="name">
              (435) 668-5171
              bandrewlewis@gmail.com
              https://github.com/userbal
            </span>
          </div>
          <div class="section">
            <h3 :style="{color: highlightColor}">Skills</h3>
            <ul>
              <li v-for="(item, index) in skills" :key="index">
                {{item}}
              </li>
            </ul>
          </div>
          <div class="section">
            <h3 :style="{color: highlightColor}">Languages</h3>
            <ul>
              <li v-for="(item, index) in languages" :key="index">
                {{item}}
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Resume',
  props: {
      highlightColor: {
        required: false,
        type: String,
        default: '#9cd2d6',
      },
      textColor: {
        required: false,
        type: String,
        default: 'black',
      },
      backgroundColor: {
        required: false,
        type: String,
        default: 'white',
      },
  },
  data() {
    return {
      skills: ['Vue.js', 'Node.js', 'Agile Development', 'Git Version Control', 'Remote Work'],
      languages: ['Javascript', 'Python', 'HTML & CSS', 'Go', 'C++'],
    }
  },
}
</script>

<style>
#container {
  display: flex;
  justify-content: center;
}

h1 {
  width: 100%
}
h5 {
  width: 100%
}

#main{
  display: flex;
  flex-direction: row;
  margin: 0px;
  padding: 0px;
}

.section-body{
  margin-bottom: 40px;
}
#main-content {
  max-width: 800px;
}

#side-bar {
  width: 245px;
  margin-left: 20px;
}

.name{
  font-weight: bold;
}

.date {
  padding: 10px;
  font-style: italic;
}

ul{
  padding: 0px;
  margin: 0px;
}
li {
  list-style: none;
  padding-bottom: 20px;
}


@media (max-width: 1117px) {
  #main {
    flex-direction: column;
  }

  #side-bar {
    margin-left: 0px;
  }
}
</style>
