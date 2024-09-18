<template>
  <header
    class="backdrop-blur border-b border-gray-200 dark:border-gray-800 -mb-px sticky top-0 z-50 lg:!border-transparent bg-gray-50 dark:bg-gray-950">
    <div class="mx-auto px-4 sm:px-6 lg:px-8 max-w-7xl flex items-center justify-between gap-3 h-[--header-height]">
      <div class="lg:flex-1 flex items-center gap-1.5">
        <NuxtLink class="flex-shrink-0 font-semibold text-xl  text-gray-900 dark:text-white flex items-end gap-1.5"
          to="/">
          <UAvatar alt="Tom Brittenden" /> <span>Tom Brittenden</span>
        </NuxtLink>
      </div>

      <ul class="items-center ring-1 ring-gray-200 dark:ring-gray-800 px-3 gap-x-0 rounded-full hidden lg:flex">
        <li v-for="link in links">
          <ULink :to="link.to"
            class="text-sm/6 flex items-center gap-1 py-2 px-4 font-medium transition-all ease-in-out duration-300 relative after:absolute after:-bottom-px after:inset-x-2 after:h-px after:rounded-full after:opacity-0 after:bg-gray-900 dark:after:bg-white after:transition-opacity"
            :class="{
              'text-gray-900 dark:text-white after:opacity-100':
                activeSection == link.id, 'text-gray-500 hover:text-gray-700 dark:text-gray-400 dark:hover:text-gray-200':
                activeSection !== link.id
            }">
            {{ link.name }} </ULink>
        </li>
      </ul>

      <div class="flex items-center justify-end lg:flex-1 gap-1.5">
        <ULink to="https://github.com/curdledSoy">
          <UIcon class="h-5 w-5" name="i-simple-icons:github" />
        </ULink>
        <ULink to="https://www.linkedin.com/in/tom-brittenden/">
          <UIcon class="h-5 w-5" name="i-simple-icons:linkedin" />
        </ULink>
        <ULink to="https://www.x.com/tom_brittenden/">
          <UIcon class="h-5 w-5" name="i-simple-icons:x" />
        </ULink>
      </div>
    </div>
  </header>
</template>

<script lang="ts" setup>
const router = useRouter()
const route = useRoute()
const links = [{ name: 'Home', to: { to: '', hash: "#home" }, id: "home" }, { name: 'Projects', to: "#projects", id: "projects" }, { name: 'Qualifications', to: "#qualifications", id: "qualifications" }, { name: 'Contact', to: "#contact", id: "contact" }]

const activeSection = useState('activeSection', () => "home")

const sections = [
  { id: 'home', offset: 0 },
  { id: 'projects', offset: 0 },
  { id: 'qualifications', offset: 0 },
  { id: 'contact', offset: 0 }
];

const updateActiveSection = () => {
  const scrollPosition = window.scrollY + window.innerHeight / 2; // Adjust for middle of screen

  for (let section of sections) {
    const element = document.getElementById(section.id);
    if (element) {
      const offsetTop = element.offsetTop;
      const offsetBottom = offsetTop + element.offsetHeight;
      section.offset = offsetTop;

      if (scrollPosition >= offsetTop && scrollPosition < offsetBottom) {
        activeSection.value = section.id;
      }
    }
  }
};

onMounted(() => {
  window.addEventListener('scroll', updateActiveSection);
});

onBeforeUnmount(() => {
  window.removeEventListener('scroll', updateActiveSection);
});
</script>