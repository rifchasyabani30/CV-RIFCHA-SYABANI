<template>
  <nav class="navbar">
    <div class="navbar-container">
      <a href="#" class="navbar-brand">Rifcha Sya'bani Fatullah</a>
      <ul class="navbar-links">
        <li><a href="#skills">Skills</a></li>
        <li><a href="#projects">Projects</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </div>
  </nav>
  <div class="container">
    <div class="left-section">
      <div class="text-content">
        <p class="im">I'm</p>
        <h1 class="name">Rifcha Sya'bani Fatullah</h1>
        <p class="profession moving">Information Technology Student</p>
        <p class="description">
          I am an Associate's Degree student in Information Technology with a strong interest and practical experience in software development through project assignments within my academic curriculum. This has enabled me to apply analytical and creative thinking in addressing technical challenges. Additionally, I have strong teamwork skills. With my background, I am ready to contribute my time and skills to make a meaningful impact.
        </p>
      </div>
    </div>
    <div class="right-section">
      <img :src="profilePic" alt="Profile Picture" />
    </div>
  </div>

  <section class="skills-experience" id="skills">
    <h2>Skills & Experience</h2>
    <p class="intro-text">
      Ready to innovate with the skills I possess and continuously grow through new experiences
    </p>

    <div class="content">
      <div class="skills">
        <h3>My Skills</h3>
        <div class="skills-grid">
          <div class="skill" v-for="skill in skills" :key="skill.name">
            <div class="skill-name">{{ skill.name }}</div>
            <div class="skill-bar">
              <div class="skill-percentage" :style="{ width: `${skill.percentage}%`, backgroundColor: skill.color }"></div>
            </div>
            <div class="percentage-label">{{ skill.percentage }}%</div>
          </div>
        </div>
      </div>

      <div class="experience">
        <div class="tabs">
          <button class="tab" :class="{ active: activeTab === 'experience' }" @click="activeTab = 'experience'">Experience</button>
          <button class="tab" :class="{ active: activeTab === 'education' }" @click="activeTab = 'education'">Education</button>
        </div>
        <div class="tab-content" v-if="activeTab === 'experience'">
          <div class="experience-grid">
            <div class="experience-item" v-for="(exp, index) in experience" :key="exp.title">
              <h4>{{ exp.title }}</h4>
              <p class="years">{{ exp.years }}</p>
              <p class="decs">{{ exp.desc }}</p>
            </div>
          </div>
        </div>
        <div class="tab-content" v-if="activeTab === 'education'">
          <div class="education-grid">
            <div class="education-item" v-for="edu in education" :key="edu.degree">
              <h4>{{ edu.institution }}</h4>
              <p class="years">{{ edu.years }}</p>
              <p class="degree">{{ edu.degree }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
      <!-- My Projects Section -->
  <section class="my-projects" id="projects">
    <h2>MY PROJECTS</h2>
    <p class="intro-text">Here are some of the projects I've worked on:</p>
    <div class="projects-grid">
      <div class="project-item" v-for="(project, index) in projects" :key="project.title">
        <!-- Carousel for project images -->
        <div class="carousel">
          <button @click="prevImage(index)" class="prev-button">‹</button>
          <img :src="project.images[project.currentImage]" alt="Project Image" />
          <button @click="nextImage(index)" class="next-button">›</button>
        </div>
        <h4>{{ project.title }}</h4>
        <p>{{ project.description }}</p>
      </div>
    </div>
  </section>

  <!-- Contact Section -->
  <section class="contact-section" id="contact">
  <h2>Contact Me</h2>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css">
  <p class="contact-intro">Feel free to get in touch with me. You can reach out to me through the following methods:</p>
  <div class="contact-grid">
    <div class="contact-item">
      <i class="fas fa-envelope"></i>
      <p>Email: <a href="mailto:rifchasyabani30@gmail.com">rifchasyabani30@gmail.com</a></p>
    </div>
    <div class="contact-item">
      <i class="fas fa-phone"></i>
      <p>Phone: +62 87773918773</p>
    </div>
    <div class="contact-item">
      <i class="fas fa-map-marker-alt"></i>
      <p>Location: Malang, Indonesia</p>
    </div>
    <div class="contact-item">
      <i class="fab fa-instagram"></i>
      <p>Instagram: <a href="https://www.instagram.com/rifchasyabani_?igsh=MTRzMjB3M29ldXEwMg==" target="_blank">rifchasyabani_</a></p>
    </div>
    <div class="contact-item">
      <i class="fab fa-linkedin"></i>
      <p>LinkedIn: <a href="http://www.linkedin.com/in/rifcha-sya-bani-fatullah-5279ab283" target="_blank">rifcha-sya-bani-fatullah</a></p>
    </div>
    <div class="contact-item">
      <i class="fab fa-github"></i>
      <p>GitHub: <a href="https://github.com/rifchasyabani30" target="_blank">rifchasyabani30</a></p>
    </div>
  </div>
</section>

</template>

<script>
import '../assets/style.css';
import profilePic from './assets/rifchaa.jpeg';
import projectOne1 from './assets/skillwave1.png';
import projectOne2 from './assets/skillwave2.jpeg';
import projectOne3 from './assets/skillwave3.png';
import projectOne4 from './assets/skillwave4.png';
import projectOne5 from './assets/skillwave5.png';
import projectOne6 from './assets/skillwave6.png';
import projectOne7 from './assets/skillwave7.png';
import projectTwo1 from './assets/kuliner 2.png';
import projectTwo2 from './assets/kuliner3.png';
import projectTwo3 from './assets/kuliner 4.png';
import projectThree1 from './assets/mock up.png';
import projectThree2 from './assets/fitur.png';
import projectThree3 from './assets/mockup2.png';
import projectThree4 from './assets/mockup3.png';
import projectThree5 from './assets/mockup4.png';
import projectFour1 from './assets/farmify.jpg';
import projectFour2 from './assets/farmify2.jpg';
import projectFour3 from './assets/farmify3.jpg';



export default {
  data() {
    return {
      profilePic,
      activeTab: 'experience',
      skills: [
        { name: 'HTML & CSS', percentage: 80, color: '#673ab7' },
        { name: 'Javascript', percentage: 80, color: '#f44336' },
        { name: 'MySQL', percentage: 60, color: '#ffeb3b' },
        { name: 'Figma', percentage: 85, color: '#000' },
        { name: 'PHP', percentage: 80, color: '#e91e63' },
        { name: 'Ms. Office', percentage: 98, color: '#03a9f4' },
      ],
      experience: [
      { title: 'Student Day Secretary', years: '2020-2023', desc: 'Drafted and managed incoming and outgoing correspondence, ensuring proper formatting and clarity. Organized and maintained the schedule for meetings and events, ensuring efficient time management. Trained in Understanding Professional Ethics.' },
      { title: 'Freelancer', years: '2023', desc: 'Developed static websites for various clients using Pingendo, focusing on clean design and user-friendly interfaces.' },
      { title: 'Department of Information Technology', years: '2020-2023', desc: 'Participating in a computer education program at PGRI Plus Senior High School Cibinong.' },

      ],
      education: [
        { institution: 'SMA Plus PGRI Cibinong', years: '2020 - 2023', degree: 'Science' },
        { institution: 'Universitas Brawijaya', years: '2023 - Present', degree: 'Information Technology' },
      ],
      projects: [
        {
          title: 'SkillWave',
          images: [projectOne1, projectOne2, projectOne3, projectOne4, projectOne5, projectOne6, projectOne7 ],
          currentImage: 0,
          description: 'Skillwave is an innovative online platform designed to provide comprehensive IT courses tailored for learners of all levels. Our mission is to empower individuals with the skills necessary to thrive in today’s technology-driven world.',
        },
        {
          title: 'Freelance',
          images: [projectTwo1, projectTwo2, projectTwo3 ],
          currentImage: 0,
          description: ' I undertook a freelance project that involved creating a dynamic and visually appealing website using Pigendo, a powerful design tool. The project aimed to provide a seamless user experience and showcase the client’s services effectively..',
        },
        {
          title: 'CoRide',
          images: [projectThree1, projectThree2, projectThree3, projectThree4, projectThree5 ],
          currentImage: 0,
          description: 'The application features a user-friendly design, making it easy for students to navigate and book rides effortlessly. With a focus on convenience and accessibility, users can quickly select their pickup and drop-off locations, view real-time pricing, and track their rides in progress.',
        },
        {
          title: 'Farmify',
          images: [projectFour1, projectFour2,projectFour3],
          currentImage: 0,
          description: 'This application is designed to assist farmers in Indonesia by providing user-friendly features tailored to their needs. The primary goal is to create an intuitive user interface (UI) that simplifies access to essential tools and resources for farming.',
        },
      ],
    };
  },
        methods: {
          nextImage(index) {
            const project = this.projects[index];
            project.currentImage = (project.currentImage + 1) % project.images.length;
          },
          prevImage(index) {
            const project = this.projects[index];
            project.currentImage =
              (project.currentImage - 1 + project.images.length) % project.images.length;
       },
    },
};
   
</script>