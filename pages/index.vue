<template>
  <!-- Modern Glass Navigation -->
  <nav class="w-full fixed z-50 top-0 backdrop-blur-md bg-white/80 shadow-sm">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between h-16 items-center">
        <div class="flex items-center">
          <div class="text-2xl font-bold bg-gradient-to-r from-blue-600 to-indigo-500 bg-clip-text text-transparent">RH.</div>
        </div>
        <div class="hidden md:flex space-x-8">
          <a v-for="nav in navigation" :key="nav.id" :href="nav.href" 
             class="text-gray-700 hover:text-indigo-600 font-medium transition-colors">
            {{ nav.name }}
          </a>
        </div>
        <div class="md:hidden">
          <button @click="mobileMenuOpen = !mobileMenuOpen" class="text-gray-700">
            <svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" 
                    d="M4 6h16M4 12h16M4 18h16" />
            </svg>
          </button>
        </div>
      </div>
    </div>
    
    <!-- Mobile menu -->
    <div v-if="mobileMenuOpen" class="md:hidden bg-white shadow-lg">
      <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3">
        <a v-for="nav in navigation" :key="nav.id" :href="nav.href" 
           class="block px-3 py-2 text-gray-700 hover:text-indigo-600 hover:bg-gray-50">
          {{ nav.name }}
        </a>
      </div>
    </div>
  </nav>

  <!-- Hero Section -->
  <section id="beranda" class="pt-24 pb-16 md:pt-32 md:pb-24 bg-gradient-to-br from-blue-50 to-indigo-50">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex flex-col md:flex-row items-center">
        <div class="md:w-1/2 mb-10 md:mb-0 md:pr-10">
          <h1 class="text-4xl md:text-5xl font-bold text-gray-900 mb-4 leading-tight">
            Hi, I'm <span class="text-indigo-600">Redita Hilmi</span>
          </h1>
          <h2 class="text-2xl md:text-3xl font-semibold text-gray-700 mb-6">
            Frontend Developer & UI Enthusiast
          </h2>
          <p class="text-lg text-gray-600 mb-8">
            I build exceptional digital experiences with Vue.js and modern web technologies.
            Passionate about creating intuitive interfaces that users love.
          </p>
          <div class="flex space-x-4">
            <a href="#contact" class="btn-primary">
              Contact Me
            </a>
            <a href="#project" class="btn-secondary">
              View Projects
            </a>
          </div>
        </div>
        <div class="md:w-1/2 flex justify-center">
          <div class="relative">
            <img src="/public/assets/me.png" alt="Redita Hilmi" 
                 class="w-64 h-64 md:w-80 md:h-80 rounded-full object-cover border-4 border-white shadow-xl">
            <div class="absolute -bottom-4 -right-4 bg-indigo-100 p-3 rounded-full shadow-md">
              <div class="bg-indigo-600 text-white p-2 rounded-full">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4" />
                </svg>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Skills Section - Designed to Impress HR -->
  <section id="skills" class="py-16 bg-white">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16">
        <span class="text-indigo-600 font-semibold">MY CAPABILITIES</span>
        <h2 class="text-3xl md:text-4xl font-bold text-gray-900 mt-2 mb-4">Professional Skills</h2>
        <p class="max-w-2xl mx-auto text-gray-600">
          I've honed these skills through various projects and continuous learning. Here's what I bring to your team:
        </p>
      </div>

      <div class="grid grid-cols-1 lg:grid-cols-2 gap-12">
        <!-- Technical Skills -->
        <div class="bg-gradient-to-br from-blue-50 to-indigo-50 p-8 rounded-2xl shadow-sm hover:shadow-md transition-shadow">
          <div class="flex items-center mb-8">
            <div class="bg-indigo-100 p-3 rounded-lg mr-4">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8 text-indigo-600" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9.75 17L9 20l-1 1h8l-1-1-.75-3M3 13h18M5 17h14a2 2 0 002-2V5a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
              </svg>
            </div>
            <h3 class="text-2xl font-bold text-gray-800">Technical Expertise</h3>
          </div>
          
          <div class="space-y-6">
            <div v-for="skill in technicalSkills" :key="skill.id" class="skill-item group">
              <div class="flex justify-between mb-2">
                <span class="font-medium text-gray-700 group-hover:text-indigo-600 transition-colors">{{ skill.name }}</span>
                <span class="text-indigo-600 font-medium">{{ skill.level }}%</span>
              </div>
              <div class="w-full bg-gray-200 rounded-full h-2.5">
                <div class="bg-indigo-600 h-2.5 rounded-full" 
                     :style="{ width: skill.level + '%' }"
                     :class="{'animate-[pulse_1.5s_infinite]': skill.level > 85}"></div>
              </div>
            </div>
          </div>
        </div>

        <!-- Professional Skills -->
        <div class="bg-gradient-to-br from-blue-50 to-indigo-50 p-8 rounded-2xl shadow-sm hover:shadow-md transition-shadow">
          <div class="flex items-center mb-8">
            <div class="bg-indigo-100 p-3 rounded-lg mr-4">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8 text-indigo-600" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0M15 7a3 3 0 11-6 0 3 3 0 016 0zm6 3a2 2 0 11-4 0 2 2 0 014 0zM7 10a2 2 0 11-4 0 2 2 0 014 0z" />
              </svg>
            </div>
            <h3 class="text-2xl font-bold text-gray-800">Professional Strengths</h3>
          </div>
          
          <div class="space-y-6">
            <div v-for="skill in professionalSkills" :key="skill.id" class="skill-item group">
              <div class="flex justify-between mb-2">
                <span class="font-medium text-gray-700 group-hover:text-indigo-600 transition-colors">{{ skill.name }}</span>
                <span class="text-indigo-600 font-medium">{{ skill.level }}%</span>
              </div>
              <div class="w-full bg-gray-200 rounded-full h-2.5">
                <div class="bg-indigo-600 h-2.5 rounded-full" 
                     :style="{ width: skill.level + '%' }"
                     :class="{'animate-[pulse_1.5s_infinite]': skill.level > 75}"></div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Projects Section -->
  <section id="project" class="py-16 bg-gray-50">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16">
        <span class="text-indigo-600 font-semibold">MY WORK</span>
        <h2 class="text-3xl md:text-4xl font-bold text-gray-900 mt-2 mb-4">Featured Projects</h2>
        <p class="max-w-2xl mx-auto text-gray-600">
          Here are some of my recent projects that demonstrate my skills and capabilities.
        </p>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div v-for="project in projects" :key="project.id" 
             class="bg-white rounded-xl overflow-hidden shadow-lg hover:shadow-xl transition-shadow group">
          <div class="relative overflow-hidden h-48">
            <img :src="project.image" :alt="project.name" 
                 class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-105">
            <div class="absolute inset-0 bg-gradient-to-t from-black/70 to-transparent"></div>
            <div class="absolute bottom-4 left-4">
              <span class="bg-indigo-600 text-white text-xs font-medium px-2.5 py-0.5 rounded">Featured</span>
            </div>
          </div>
          <div class="p-6">
            <h3 class="text-xl font-bold text-gray-900 mb-2">{{ project.name }}</h3>
            <p class="text-gray-600 mb-4">{{ project.deskripsi }}</p>
            <div class="flex justify-between items-center">
              <a :href="project.subject" target="_blank" 
                 class="text-indigo-600 hover:text-indigo-800 font-medium flex items-center">
                View Project
                <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4 ml-1" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14" />
                </svg>
              </a>
              <div class="flex space-x-2">
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Contact Section -->
  <section id="contact" class="py-16 bg-white">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16">
        <span class="text-indigo-600 font-semibold">GET IN TOUCH</span>
        <h2 class="text-3xl md:text-4xl font-bold text-gray-900 mt-2 mb-4">Let's Work Together</h2>
        <p class="max-w-2xl mx-auto text-gray-600">
          Interested in working together or have any questions? Feel free to reach out!
        </p>
      </div>

      <div class="max-w-3xl mx-auto bg-gradient-to-br from-blue-50 to-indigo-50 rounded-2xl p-8 shadow-sm">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
          <div>
            <h3 class="text-xl font-semibold text-gray-800 mb-4">Contact Information</h3>
            <div class="space-y-4">
              <div class="flex items-start">
                <div class="bg-indigo-100 p-2 rounded-lg mr-4">
                  <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-indigo-600" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
                  </svg>
                </div>
                <div>
                  <h4 class="font-medium text-gray-700">Email</h4>
                  <a href="mailto:your.email@example.com" class="text-indigo-600 hover:underline">redita.hilmi@example.com</a>
                </div>
              </div>
              <div class="flex items-start">
                <div class="bg-indigo-100 p-2 rounded-lg mr-4">
                  <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-indigo-600" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z" />
                  </svg>
                </div>
                <div>
                  <h4 class="font-medium text-gray-700">Phone</h4>
                  <a href="tel:+1234567890" class="text-indigo-600 hover:underline">+62 812 3456 7890</a>
                </div>
              </div>
            </div>

            <div class="mt-8">
              <h3 class="text-xl font-semibold text-gray-800 mb-4">Connect With Me</h3>
              <div class="flex justify-center space-x-6">
        <!-- LinkedIn -->
        <a href="https://www.linkedin.com/in/redita-hilmi-al-paridz-a71421347/" 
           class="text-gray-700 hover:text-blue-600 transition-colors duration-300">
          <span class="sr-only">LinkedIn</span>
          <i class="fab fa-linkedin text-3xl"></i>
        </a>
        
        <!-- Instagram -->
        <a href="https://www.instagram.com/reditahilmi" 
           class="text-gray-700 hover:text-pink-600 transition-colors duration-300">
          <span class="sr-only">Instagram</span>
          <i class="fab fa-instagram text-3xl"></i>
        </a>
        
        <!-- GitHub -->
        <a href="https://github.com/ReditaHilmial-paridz" 
           class="text-gray-700 hover:text-gray-900 transition-colors duration-300">
          <span class="sr-only">GitHub</span>
          <i class="fab fa-github text-3xl"></i>
        </a>
        
        <!-- Email -->
        <a href="mailto:your.email@example.com" 
           class="text-gray-700 hover:text-red-600 transition-colors duration-300">
          <span class="sr-only">Email</span>
          <i class="fas fa-envelope text-3xl"></i>
        </a>
      </div>
            </div>
          </div>

          <div>
            <form action="https://formspree.io/f/xyzwdyyq" method="POST">
              <div class="space-y-4">
                <div>
                  <label for="name" class="block text-sm font-medium text-gray-700 mb-1">Nama Anda</label>
                  <input type="text" id="name" name="name" required
                        class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-indigo-500 focus:border-indigo-500">
                </div>
                <div>
                  <label for="email" class="block text-sm font-medium text-gray-700 mb-1">Email Anda</label>
                  <input type="email" id="email" name="email" required
                        class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-indigo-500 focus:border-indigo-500">
                </div>
                <div>
                  <label for="message" class="block text-sm font-medium text-gray-700 mb-1">Pesan</label>
                  <textarea id="message" name="message" rows="4" required
                            class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-indigo-500 focus:border-indigo-500"></textarea>
                </div>
                <button type="submit" 
                        class="w-full bg-indigo-600 text-white py-2 px-4 rounded-lg hover:bg-indigo-700 transition-colors font-medium">
                  Kirim Pesan
                </button>
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Footer -->
  <footer class="bg-gray-900 text-white py-8">
      <div class="mt-8 pt-8 border-t border-gray-800 text-center text-gray-400 text-sm">
        <p>© {{ new Date().getFullYear() }} Redita Hilmi Al-paridz. All rights reserved.</p>
      </div>
  </footer>
</template>

<script setup>
import { ref } from 'vue';

const mobileMenuOpen = ref(false);

const navigation = [
  { id: 1, name: 'About', href: '#beranda' },
  { id: 2, name: 'Skills', href: '#skills' },
  { id: 3, name: 'Projects', href: '#project' },
  { id: 4, name: 'Contact', href: '#contact' },
];

const db_projects = ref([
  {
    id: 1,
    name: 'School Website',
    deskripsi: 'Comprehensive website for SMKN 4 TASIKMALAYA with information portal and admin dashboard.',
    subject: 'https://ujikom-final.vercel.app/',
    image: '/assets/project1.png'
  },
  {
    id: 2,
    name: 'Digital Canteen',
    deskripsi: 'SPW Digital streamlines school canteen operations with order management and reporting.',
    subject: 'hhttps://spw-canteen.vercel.app/',
    image: '/assets/project2.png'  
  },
  {
    id: 3,
    name: 'Digital Library',
    deskripsi: 'Modern library system with digital visitor book and book management features.',
    subject: 'https://tefa-redita.vercel.app/',
    image: '/assets/project3.png'
  },
  {
    id: 4,
    name: 'ecosphere',
    deskripsi: 'This website is designed to help children learn to protect nature in a fun way',
    subject: 'https://ecosphere-fun.vercel.app/',
    image: '/assets/project4.png'
  },
]);

const projects = ref([...db_projects.value]);

const db_technicalSkills = ref([
  { id: 1, name: 'Vue.js', level: 80 },
  { id: 2, name: 'JavaScript', level: 83 },
  { id: 3, name: 'HTML5', level: 87 },
  { id: 4, name: 'CSS3', level: 85},
  { id: 5, name: 'Figma', level: 80},
  { id: 6, name: 'Excel', level: 81}
]);

const db_professionalSkills = ref([
  { id: 7, name: 'Problem Solving', level: 80},
  { id: 8, name: 'Teamwork', level: 87},
  { id: 9, name: 'Communication', level: 80},
  { id: 10, name: 'Project Management', level: 78},
  { id: 11, name: 'Creativity', level: 76},
  { id: 12, name: 'Adaptability', level: 75}
]);

const technicalSkills = ref([...db_technicalSkills.value]);
const professionalSkills = ref([...db_professionalSkills.value]);

</script>

<style>
@import url('https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css');
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');

html {
  scroll-behavior: smooth;
  font-family: 'Inter', sans-serif;
}

.btn-primary {
  @apply bg-indigo-600 text-white px-6 py-3 rounded-lg font-medium hover:bg-indigo-700 transition-colors shadow-sm hover:shadow-md;
}

.btn-secondary {
  @apply border border-indigo-600 text-indigo-600 px-6 py-3 rounded-lg font-medium hover:bg-indigo-50 transition-colors shadow-sm hover:shadow-md;
}

/* Animation for skill bars with >85% */
@keyframes pulse {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.7; }
}

.animate-\[pulse_1\.5s_infinite\] {
  animation: pulse 1.5s infinite;
}

/* Smooth transitions */
.transition-colors {
  transition-property: color, background-color, border-color, fill, stroke;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 150ms;
}

.transition-shadow {
  transition-property: box-shadow;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 150ms;
}

.transition-transform {
  transition-property: transform;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 300ms;
}
</style>
