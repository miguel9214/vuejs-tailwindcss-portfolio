<script>
import feather from 'feather-icons';

export default {
  name: 'Home',
  data: () => {
    return {
      theme: '',
    };
  },
  created() {
    this.theme = localStorage.getItem('theme') || 'light';
  },
  mounted() {
    feather.replace();
    this.theme = localStorage.getItem('theme') || 'light';
  },
  updated() {
    feather.replace();
  },
  methods: {
    descargarHojaDeVida() {
      const hojaDeVidaURL = 'file/Miguel-Resume.pdf';
      this.descargarArchivo(hojaDeVidaURL, 'Miguel-Resume.pdf');
    },

    descargarArchivo(url, nombre) {
      const link = document.createElement('a');
      link.href = url;
      link.download = nombre;

      document.body.appendChild(link);
      link.click();

      document.body.removeChild(link);
    },
  },
};
</script>

<template>
  <section class="flex flex-col sm:justify-between items-center sm:flex-row mt-12 sm:mt-10">
    <!-- Banner left contents -->
    <div class="w-full md:w-1/3 text-left">
      <!-- ... (código anterior) ... -->
      <div class="flex justify-center sm:block">
        <a
          @click.prevent="descargarHojaDeVida"
          download="Miguel-Resume.pdf"
          href="file/Miguel-Resume.pdf"
          class="flex justify-center items-center w-36 sm:w-48 mt-12 mb-6 sm:mb-0 text-lg border border-indigo-200 dark:border-ternary-dark py-2.5 sm:py-3 shadow-lg rounded-lg bg-indigo-50 focus:ring-1 focus:ring-indigo-900 hover:bg-indigo-500 text-gray-500 hover:text-white duration-500"
          aria-label="Download Resume"
        >
          <i
            data-feather="arrow-down-circle"
            class="ml-0 sm:ml-1 mr-2 sm:mr-3 w-5 sm:w-6 duration-100"
          ></i>
          <span
            class="text-sm sm:text-lg font-general-medium duration-100"
            >Descargar CV</span
          ></a
        >
      </div>
    </div>

    <!-- Banner right illustration -->
    <div class="w-full md:w-2/3 text-right float-right">
      <img v-if="theme === 'light'" src="@/assets/images/developer.svg" alt="Developer" />
      <img v-else src="@/assets/images/developer-dark.svg" alt="Developer" />
    </div>
  </section>
</template>

<style scoped>

</style>
