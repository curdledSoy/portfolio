<template>
  <UContainer>
    <!-- Hero Section -->
    <section id="home" class="flex flex-wrap gap-4 min-h-[100vh] items-center px-4 sm:px-6 lg:px-8">
      <div class="pt-4 flex flex-grow">
        <div>
          <h2 class="text-5xl font-bold text-gray-800 dark:text-white">
            Hi There! <br /> I'm Tom Brittenden
          </h2>
          <p class="text-lg mt-4 text-gray-600 dark:text-gray-400">
            I'm a Software Developer with a passion for Fullstack Development
          </p>
        </div>
      </div>
      <div class="border-light-50 border h-80 w-80 rounded-full overflow-clip">
        <!-- /images/gradPhoto.png -->

        <img src="" class="object-cover" />
      </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto py-16 mt-16">
      <div class="text-center">
        <h2 class="text-4xl font-bold text-gray-800 dark:text-white">My Projects</h2>
        <p class="mt-4 text-lg text-gray-600 dark:text-gray-400">
          Some of the projects I've worked on recently.
        </p>
      </div>
      <div class="mt-12 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div class="shadow-lg rounded-lg p-6 bg-white dark:bg-gray-800 hover:shadow-2xl transition"
          v-for="project in projects" :key="project._id">
          <h3 class="text-xl font-semibold text-gray-800 dark:text-white">{{ project.title }}</h3>
          <p class="mt-2 text-sm text-gray-600 dark:text-gray-400">
            {{ project.description }}
          </p>
          <UButton @click="showProject(project)">
            See More
          </UButton>

        </div>


      </div>
    </section>

    <!-- Qualifications Section -->
    <section id="qualifications" class="px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto py-16 mt-16">
      <div class="text-center">
        <h2 class="text-4xl font-bold text-gray-800 dark:text-white">Qualifications</h2>
        <p class="mt-4 text-lg text-gray-600 dark:text-gray-400">
          Here are my professional and educational qualifications.
        </p>
      </div>
      <div class="mt-12 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div class="shadow-lg rounded-lg p-6 bg-white dark:bg-gray-800 hover:shadow-2xl transition">
          <h3 class="text-xl font-semibold text-gray-800 dark:text-white">Bachelor of Science in Computer Science</h3>
          <p class="mt-2 text-sm text-gray-600 dark:text-gray-400">
            XYZ University
          </p>
        </div>
        <div class="shadow-lg rounded-lg p-6 bg-white dark:bg-gray-800 hover:shadow-2xl transition">
          <h3 class="text-xl font-semibold text-gray-800 dark:text-white">Certified Full Stack Developer</h3>
          <p class="mt-2 text-sm text-gray-600 dark:text-gray-400">
            ABC Bootcamp
          </p>
        </div>
        <div class="shadow-lg rounded-lg p-6 bg-white dark:bg-gray-800 hover:shadow-2xl transition">
          <h3 class="text-xl font-semibold text-gray-800 dark:text-white">JavaScript Advanced Certification</h3>
          <p class="mt-2 text-sm text-gray-600 dark:text-gray-400">
            Online Academy
          </p>
        </div>
        <div class="shadow-lg rounded-lg p-6 bg-white dark:bg-gray-800 hover:shadow-2xl transition">
          <h3 class="text-xl font-semibold text-gray-800 dark:text-white">Certified ScrumMaster (CSM)</h3>
          <p class="mt-2 text-sm text-gray-600 dark:text-gray-400">
            Scrum Alliance
          </p>
        </div>
      </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto py-16 mt-16">
      <div class="text-center">
        <h2 class="text-4xl font-bold text-gray-800 dark:text-white">Contact Me</h2>
        <p class="mt-4 text-lg text-gray-600 dark:text-gray-400">
          Feel free to reach out for collaboration or just a chat.
        </p>
      </div>

      <div class="mt-12 max-w-2xl mx-auto bg-white dark:bg-gray-700 shadow-lg rounded-lg p-8">
        <form class="space-y-6">
          <!-- Name Field -->
          <div>
            <label for="name" class="block text-sm font-medium text-gray-700 dark:text-gray-300">Name</label>
            <input type="text" id="name"
              class="mt-2 block w-full border border-gray-300 dark:border-gray-600 rounded-md shadow-sm py-3 px-4 focus:ring-indigo-500 focus:border-indigo-500 dark:bg-gray-800 dark:focus:border-indigo-500 transition"
              placeholder="Enter your name">
          </div>

          <!-- Email Field -->
          <div>
            <label for="email" class="block text-sm font-medium text-gray-700 dark:text-gray-300">Email</label>
            <input type="email" id="email"
              class="mt-2 block w-full border border-gray-300 dark:border-gray-600 rounded-md shadow-sm py-3 px-4 focus:ring-indigo-500 focus:border-indigo-500 dark:bg-gray-800 dark:focus:border-indigo-500 transition"
              placeholder="Enter your email">
          </div>

          <!-- Message Field -->
          <div>
            <label for="message" class="block text-sm font-medium text-gray-700 dark:text-gray-300">Message</label>
            <textarea id="message" rows="6"
              class="mt-2 block w-full border border-gray-300 dark:border-gray-600 rounded-md shadow-sm py-3 px-4 focus:ring-indigo-500 focus:border-indigo-500 dark:bg-gray-800 dark:focus:border-indigo-500 transition"
              placeholder="Write your message..."></textarea>
          </div>

          <!-- Submit Button -->
          <div>
            <button type="submit"
              class="w-full bg-indigo-600 hover:bg-indigo-700 text-white py-3 px-4 rounded-md shadow-lg font-semibold transition hover:shadow-xl">
              Send Message
            </button>
          </div>
        </form>
      </div>
    </section>
  </UContainer>
</template>

<script lang="ts" setup>
import type { ParsedContent } from '@nuxt/content';
import { ProjectDetails } from '#components';

const modal = useModal()

const { data: projects } = await useAsyncData('projects', () => queryContent('projects').limit(10).find())

const currentProject = useState<ParsedContent | null>("currentProject")

function showProject(project: ParsedContent) {
  currentProject.value = project
  modal.open(ProjectDetails, {
    project

  })
}

</script>
