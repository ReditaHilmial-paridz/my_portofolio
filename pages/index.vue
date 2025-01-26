<template>
      <div class="w-full sticky z-10 top-0 glass text-black shadow">
      <div class="navbar">
        <div class="navbar-start">
          <div class="dropdown">
            <div tabindex="0" role="button" class="btn btn-ghost lg:hidden">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24"
                stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h8m-8 6h16" />
              </svg>
            </div>
            <ul tabindex="0" class="menu menu-sm dropdown-content bg-base-100 rounded-box z-[1] mt-3 w-52 p-2 shadow">
              <li>
              <a href="#beranda">About</a>
          </li>
          <li>
            <a href="#project">Project</a>
          </li>
          <li>
            <a href="#contact">Contact</a>
          </li>
            </ul>
          </div>
            <div>RH</div>

        </div>
        <div class="navbar-end hidden lg:flex">
          <ul class="menu menu-horizontal px-1">
            <li>
              <div class="dropdown dropdown-bottom dropdown-end dropdown-hover">
              </div>
            </li>
            <li>
              <a href="#beranda">About</a>
          </li>
          <li>
            <a href="#project">Project</a>
          </li>
          <li>
            <a href="#contact">Contact</a>
          </li>
          </ul>
        </div>
      </div>
    </div>

    <section id="beranda">
      <div class="hero bg-gradient-to-r from-blue-200 via-teal-300 to-indigo-200 min-h-screen animate-gradient-x">
        <div class="hero-content flex-col lg:flex-row">
          <div class="avatar">
            <div class="w-96 rounded-full grid-cols-4" style="object-fit: cover;">
              <img src="/public/assets/me.png" />
            </div>
          </div>
          <div>
            <h1 class="text-5xl font-bold">Redita Hilmi Al-paridz</h1>
            <p class="py-6">
              I am a passionate junior web developer dedicated to crafting clean and responsive websites. 
              With a strong foundation in modern web technologies, I aim to bring ideas to life through code and creativity.
            </p>
            <p class="py-2 text-lg">
              Let’s build something amazing together!
            </p>
          </div>
        </div>
      </div>
    </section>

    <section id="project">
    <div class="hero min-h-screen mx-auto px-8 lg:px-35" style="padding-bottom: 10px;">
  <div class="flex flex-col items-center">
    <h1 class="text-4xl font-bold mb-4">Project</h1>
    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
      <div v-for="project in projects" :key="project.id" class="card bg-base-100 w-full max-w-sm shadow-xl bg-gray-100 mx-auto">
        <figure class="m-0">
          <img :src="project.image" :alt="project.name" class="rounded-xl" />
        </figure>
        <div class="card-body items-center text-center p-4">
          <h2 class="card-title">{{ project.name }}</h2>
          <p>{{ project.deskripsi }}</p>
          <div class="card-actions">
            <a :href="project.subject" class="btn btn-primary">Lihat</a>
          </div>
        </div>
      </div>
    </div>
  </div>
  </div>
    </section>
    <section id="contact" class="bg-gray-100 py-12">
  <div class="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8">
    <h2 class="text-3xl font-bold text-center text-gray-800 mb-8">Contact Me</h2>
    <div class="bg-white shadow-md rounded-lg p-6">
      <form action="#" method="POST" class="space-y-6">
        <div>
          <label for="name" class="block text-sm font-medium text-gray-700">Your Name</label>
          <input
            type="text"
            id="name"
            name="name"
            required
            class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
            placeholder="Name"
          />
        </div>
        <div>
          <label for="email" class="block text-sm font-medium text-gray-700">Email Address</label>
          <input
            type="email"
            id="email"
            name="email"
            required
            class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
            placeholder="you@example.com"
          />
        </div>
        <div>
          <label for="message" class="block text-sm font-medium text-gray-700">Message</label>
          <textarea
            id="message"
            name="message"
            rows="4"
            required
            class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
            placeholder="Write your message here..."
          ></textarea>
        </div>
        <div class="text-center">
          <button
            type="submit"
            class="px-6 py-2 text-white bg-indigo-600 hover:bg-indigo-700 rounded-md focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2"
          >
            Send Message
          </button>
        </div>
      </form>
    </div>
    <div class="mt-8 text-center text-gray-600">
      <p>Or reach me on</p>
      <div class="flex justify-center space-x-4 mt-4">
        <a href="https://www.linkedin.com/in/redita-hilmi-al-paridz-a71421347/" class="text-gray-800 hover:text-indigo-600">
          <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6" viewBox="0 0 24 24" fill="currentColor">
            <path d="M22.225 0H1.775C.795 0 0 .795 0 1.775v20.45C0 23.205.795 24 1.775 24h20.45c.98 0 1.775-.795 1.775-1.775V1.775C24 .795 23.205 0 22.225 0zM7.005 20.285H3.88V9h3.125v11.285zm-1.562-13.038c-1.002 0-1.78-.815-1.78-1.818s.778-1.818 1.78-1.818c1.004 0 1.78.815 1.78 1.818s-.776 1.818-1.78 1.818zm14.66 13.038h-3.125v-5.25c0-1.25-.022-2.857-1.875-2.857-1.878 0-2.165 1.466-2.165 2.976v5.131h-3.125v-11.285h3.125v1.544h.045c.444-.832 1.537-1.715 3.164-1.715 3.386 0 4.008 2.23 4.008 5.132v6.324z"/>
          </svg>
        </a>
        <a href="https://www.instagram.com/reditahilmi" class="text-gray-800 hover:text-indigo-600">
          <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6" viewBox="0 0 24 24" fill="currentColor">
            <path d="M12 2.163c3.2 0 3.582.012 4.85.07 1.17.058 2.036.248 2.635.537.596.288 1.06.652 1.506 1.097.446.445.81.91 1.097 1.506.289.599.479 1.465.537 2.635.058 1.268.07 1.65.07 4.85s-.012 3.582-.07 4.85c-.058 1.17-.248 2.036-.537 2.635-.288.596-.652 1.06-1.097 1.506-.445.446-.91.81-1.506 1.097-.599.289-1.465.479-2.635.537-1.268.058-1.65.07-4.85.07s-3.582-.012-4.85-.07c-1.17-.058-2.036-.248-2.635-.537-.596-.288-1.06-.652-1.506-1.097-.445-.445-.81-.91-1.097-1.506-.289-.599-.479-1.465-.537-2.635-.058-1.268-.07-1.65-.07-4.85s.012-3.582.07-4.85c.058-1.17.248-2.036.537-2.635.288-.596.652-1.06 1.097-1.506.445-.446.91-.81 1.506-1.097.599-.289 1.465-.479 2.635-.537 1.268-.058 1.65-.07 4.85-.07zm0-2.163c-3.253 0-3.644.012-4.92.071-1.283.058-2.234.248-3.097.537-.854.289-1.597.666-2.35 1.419-.753.754-1.131 1.497-1.419 2.35-.289.863-.479 1.814-.537 3.097-.059 1.276-.071 1.667-.071 4.92s.012 3.644.071 4.92c.058 1.283.248 2.234.537 3.097.288.854.666 1.597 1.419 2.35.753.753 1.497 1.131 2.35 1.419.863.289 1.814.479 3.097.537 1.276.059 1.667.071 4.92.071s3.644-.012 4.92-.071c1.283-.058 2.234-.248 3.097-.537.854-.288 1.597-.666 2.35-1.419.753-.753 1.131-1.497 1.419-2.35.289-.863.479-1.814.537-3.097.059-1.276.071-1.667.071-4.92s-.012-3.644-.071-4.92c-.058-1.283-.248-2.234-.537-3.097-.288-.854-.666-1.597-1.419-2.35-.753-.753-1.497-1.131-2.35-1.419-.863-.289-1.814-.479-3.097-.537-1.276-.059-1.667-.071-4.92-.071zm0 5.838c-3.41 0-6.184 2.774-6.184 6.184s2.774 6.184 6.184 6.184 6.184-2.774 6.184-6.184-2.774-6.184-6.184-6.184zm0 10.184c-2.218 0-4.184-1.966-4.184-4.184s1.966-4.184 4.184-4.184 4.184 1.966 4.184 4.184-1.966 4.184-4.184 4.184zm5.907-9.217c0 .77-.623 1.394-1.394 1.394-.771 0-1.394-.623-1.394-1.394 0-.77.623-1.394 1.394-1.394.771 0 1.394.623 1.394 1.394z"/>
          </svg>
        </a>
        <a href="https://github.com/ReditaHilmial-paridz" class="text-gray-800 hover:text-indigo-600">
          <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6" viewBox="0 0 24 24" fill="currentColor">
            <path d="M12 0C5.37 0 0 5.37 0 12c0 5.304 3.438 9.8 8.205 11.397.6.11.82-.26.82-.577 0-.285-.01-1.038-.015-2.037-3.338.727-4.039-1.612-4.039-1.612-.547-1.39-1.334-1.757-1.334-1.757-1.091-.744.083-.73.083-.73 1.21.087 1.846 1.242 1.846 1.242 1.075 1.842 2.823 1.309 3.513.998.11-.779.42-1.308.764-1.609-2.667-.307-5.467-1.334-5.467-5.926 0-1.307.468-2.38 1.236-3.22-.124-.308-.535-.926.117-1.91 0 0 1.008-.322 3.309 1.23C9.62 7.396 10.804 7 12 7c1.196 0 2.38.396 3.178.946 2.301-1.553 3.309-1.23 3.309-1.23.653.984.241 1.602.117 1.91.768.84 1.236 1.913 1.236 3.22 0 4.595-2.802 5.618-5.47 5.92.43.372.818 1.104.818 2.226 0 1.61-.015 2.91-.015 3.295 0 .318.217.692.82.577C20.565 21.799 24 17.304 24 12c0-6.63-5.37-12-12-12z"/>
          </svg>
        </a>
      </div>

        <p>Copyright © by Redita</p>
    </div>
  </div>
</section>



  </template>
  <style>
html{
  scroll-behavior: smooth;
}
  @keyframes gradient-x {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
  }
  .animate-gradient-x {
    background-size: 200% 200%;
    animation: gradient-x 8s ease infinite;
  }
</style>
<script setup>


// Data guru dengan properti `image`
const db_projects = ref([
  {
    id: 1,
    name: 'WEB SEKOLAH',
    deskripsi:'Website ini dirancang untuk menjadi pusat informasi utama mengenai SMKN 4 TASIKMALAYA',
    subject:'https://github.com/ReditaHilmial-paridz/ujikom-final',
    image: '/assets/project1.png'
  },
  {
    id: 2,
    name: 'SPW DIGITAL',
    deskripsi:'Website kantin ini dirancang untuk mendukung efisiensi operasional kantin sekolah.',
    subject:'https://github.com/ReditaHilmial-paridz/SPW_CANTEEN',
    image:'/assets/project2.png'  
  },
  {
    id: 3,
    name: 'PERPUSTAKAAN DIGITAL',
    deskripsi:'website ini dirancang untuk membantu pengunjung dalam mengisi buku kunjungan supaya lebih cepat',
    subject:'https://github.com/ReditaHilmial-paridz/Tefa-perpus-digital',
    image: '/assets/project3.png'
  },
    ]);
const projects = ref([...db_projects.value]); // Semua data diambil


</script>