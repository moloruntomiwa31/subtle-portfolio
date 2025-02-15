<template>
  <NavBar />
  <!-- Hero -->
  <div class="bg-black bg-texture">
    <div
      class="flex flex-col items-center justify-center text-center p-12 h-screen"
    >
      <p class="uppercase tracking-wider text-white">Hello, my name is</p>
      <span class="w-16 h-0.5 bg-white"></span>
      <h1 class="text-5xl md:text-6xl font-semibold mt-2 text-white">
        Oluwafemi Aderibigbe
      </h1>
      <p class="text-2xl md:text-3xl text-white mt-2">
        Technical Business Analyst
      </p>
      <div>
        <p class="text-lg text-white mt-4 max-w-2xl">
          I specialize in bridging the gap between business needs and technical
          solutions. With a strong background in data analysis, project
          management, and software development, I help organizations achieve
          their goals through innovative technology solutions.
        </p>
        <div class="flex items-center justify-center mt-4">
          <a
            class="w-12 h-12 rounded-full flex justify-center items-center bg-white cursor-pointer"
            v-for="link in socialLinks"
            :key="link.name"
            :href="link.url"
          >
            <Icon
              :name="link.icon"
              class="mx-2"
              size="2rem"
              style="color: black"
            />
          </a>
        </div>
      </div>
    </div>

    <!-- About -->
    <div id="about" class="p-12">
      <div class="flex flex-col justify-center items-center text-center">
        <p class="text-2xl font-semibold text-gray-200">About Me</p>
        <p class="text-lg text-gray-300 mt-4 max-w-2xl">
          A Technical Business Analyst with 6 years expertise in digital
          transformation, process optimization, and system integration. I drive
          innovation and continuous improvement in fast-paced tech environments.
        </p>
      </div>

      <div
        class="flex flex-col md:flex-row md:justify-between items-center gap-8 mt-8"
      >
        <div class="md:w-1/2 flex flex-col gap-8 justify-between">
          <div class="flex flex-col">
            <p class="uppercase tracking-wider text-white">Skills</p>
            <span class="w-12 h-0.5 bg-white"></span>
            <div class="grid md:grid-cols-3 grid-cols-2 gap-4 mt-4">
              <Badge v-for="skill in skills" :content="skill" />
            </div>
          </div>
          <div class="flex flex-col">
            <p class="uppercase tracking-wider text-white">Tools</p>
            <span class="w-12 h-0.5 bg-white"></span>
            <div class="grid md:grid-cols-3 grid-cols-3 gap-4 mt-4">
              <Badge v-for="tool in tools" :content="tool" />
            </div>
          </div>
        </div>

        <div id="experience" class="md:w-1/2 mt-8">
          <div class="flex flex-col items-left">
            <p class="uppercase tracking-wider text-white">Experiences</p>
            <span class="w-12 h-0.5 bg-white"></span>
            <div class="flex flex-col gap-4 mt-4 w-full max-w-4xl">
              <div
                v-for="experience in experiences"
                :key="experience.id"
                class="flex flex-col md:flex-row items-start md:items-center"
              >
                <div
                  class="w-2 h-2 bg-white hidden md:block rounded-full mt-1 md:mt-0"
                ></div>
                <div class="flex-1 md:ml-4 mt-2 md:mt-0">
                  <h3 class="text-xl font-semibold">{{ experience.title }}</h3>
                  <p class="text-gray-400">
                    {{ experience.company }} - {{ experience.period }}
                  </p>
                  <p class="text-gray-300 mt-2">{{ experience.description }}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Projects -->
    <div id="projects" class="p-12">
      <div class="flex flex-col justify-center items-center text-center">
        <p class="text-2xl font-semibold text-white">Projects</p>
        <p class="text-lg text-gray-200 mt-4 max-w-2xl"></p>
      </div>
      <div class="flex flex-col md:flex-row justify-center items-center mt-8">
        <div
          v-for="project in projects"
          :key="project.id"
          class="m-4 p-4 border flex flex-col justify-between border-gray-300 rounded-lg shadow-lg min-h-[450px] max-h-fit w-full md:w-1/3"
        >
          <h3 class="text-xl font-semibold text-gray-200">
            {{ project.title }}
          </h3>
          <p class="text-gray-400 mt-2">{{ project.description }}</p>
          <a
            :href="project.githubUrl"
            class="text-blue-500 mt-4 inline-block group"
            target="_blank"
          >
            View on GitHub
            <span
              class="inline-block transform group-hover:translate-x-1 transition-transform duration-200"
            >
              &#8599;
            </span>
          </a>
        </div>
      </div>
    </div>
  </div>

  <Footer />
</template>

<script setup lang="ts">
const socialLinks = [
  {
    name: "LinkedIn",
    icon: "mdi:linkedin",
    url: "https://www.linkedin.com/in/oluwafemi-aderibigbe-00417b20b/",
  },
];
const skills = [
  "Requirement Engineering",
  "Process Optimization",
  "Gap Analysis",
  "User Acceptance Testing",
  "Wireframing & Prototyping",
  "API Development",
  "Agile and PRINCE2 Methodologies",
  "Data Technical Analysis",
  "UML Diagramming",
];
const tools = [
  "SQL",
  "Power BI",
  "Excel",
  "Data Modelling",
  "CI/CD Pipelines",
  "Figma",
  "Balsamiq",
  "Visio",
  "Lucidchart",
  "JIRA",
  "Trello",
  "Scrum",
  "Kanban",
  "PRINCE2",
];
const experiences = [
  {
    id: 1,
    title: "IT Business Analyst",
    company: "Neezerchain Digital Ltd",
    period: "April 2022 - Present",
    description:
      "Neezerchain Digital is a technology company specializing in providing digital solutions to businesses by offering a full cycle of software and application design, branding, and management transformation providing cutting edge solutions. At Neezerchain, I manage digital projects lifecycle from the project initiation stage to the closing of the project using project management methodologies while delivering robust business solutions initiatives.",
  },
  {
    id: 2,
    title: "Project Manager",
    company: "23rd Designs",
    period: "January 2021 - April 2022",
    description:
      "23RDESIGNS is a technology company specializing in developing advanced technological platforms. I played crucial roles in managing website and mobile app development projects, API integrations, and lead cloud transformation initiatives to enhance operational agility and scalability.",
  },
  {
    id: 3,
    title: "Junior Business Analyst",
    company: "TeilyTech Ltd",
    period: "March 2019 - January 2021",
    description:
      "Teily Tech is a technology company dedicated to delivering innovative solutions across various digital domains. At TeilyTech, I developed business requirement documents, functional specification documents, detailing system functionalities and user requirements as well as process flow diagrams using Visio and Lucidchart to illustrate operational improvements. Additionally, I created user Stories and acceptance criteria in line with Agile methodologies, providing detailed stakeholder reports.",
  },
];

const projects = ref([
  {
    id: 1,
    title: "Movie Discovery App",
    description:
      "Led and managed the end-to-end development of a movie and TV series discovery app, designed to provide users with an immersive browsing experience. The application allows users to explore trending movies in real time, view detailed descriptions, cast information, and ratings, filter content based on genres, release dates, and popularity, save favorite movies and TV shows for easy access and seamlessly integrate with third-party APIs for up-to-date movie data.",
    githubUrl: "https://github.com/moloruntomiwa31/cinemax",
  },
  {
    id: 2,
    title: "Developer Link Sharing App",
    description:
      "Led the development of a cutting-edge platform designed to empower developers with seamless tools to create, preview, and share custom links and professional profiles. Played a pivotal role in architecting the system, overseeing development sprints, and ensuring a high-performance, responsive, and industry-standard product. The platform features a customizable profile builder, enabling developers to effectively showcase their skills, projects, and portfolios. Additionally, it incorporates real-time link preview functionality, enhancing cross-platform sharing and engagement.",
    githubUrl: "https://github.com/moloruntomiwa31/devlinks",
  },
]);
</script>
