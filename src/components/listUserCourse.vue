<template>
  <div id="main">
    <div class="max-w-screen-xl mx-auto">
      <div class="relative overflow-x-auto shadow-md sm:rounded-lg">
        <table class="w-full text-sm text-left text-gray-500 dark:text-gray-400">
          <thead class="text-xs text-gray-700 uppercase bg-gray-50 dark:bg-gray-700 dark:text-gray-400">
            <tr>

              <th scope="col" class="px-6 md:px-20 py-3">
                Name
              </th>
              <th scope="col" class="px-6 md:px-20 py-3">
                Roles
              </th>
              <th scope="col" class="px-6 md:px-20 py-3">
                Group
              </th>
              <th scope="col" class="px-6 md:px-20 py-3">
                Last Access
              </th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="(product, index) in paginatedProducts" :key="index"
              class="bg-white border-b dark:bg-gray-800 dark:border-gray-700 hover:bg-gray-50 dark:hover:bg-gray-600">

              <th scope="row" class="px-6 md:px-20 py-4 font-medium text-gray-900 whitespace-nowrap dark:text-white">
                {{ product.name }}
              </th>
              <td class="px-6 md:px-20 py-4">
                {{ product.roles }}
              </td>
              <td class="px-6 md:px-20 py-4">
                {{ product.groups }}
              </td>
              <td class="px-6 md:px-20 py-4">
                {{ product.LastAccess }}
              </td>

            </tr>
          </tbody>
        </table>
      </div>
      <!-- Tampilkan pagination di bawah tabel -->
      <div class="flex justify-end mt-4">
        <ul class="flex space-x-2">
          <!-- Tombol "Previous" -->
          <li>
            <button @click="prevPage" :disabled="currentPage === 1" class="px-3 py-1 rounded bg-blue-500 text-white">
              Previous
            </button>
          </li>

          <!-- Daftar halaman -->
          <li v-for="page in totalPages" :key="page">
            <button @click="gotoPage(page)" :class="{ 'bg-blue-500 text-white': currentPage === page }"
              class="px-3 py-1 rounded">
              {{ page }}
            </button>
          </li>

          <!-- Tombol "Next" -->
          <li>
            <button @click="nextPage" :disabled="currentPage === totalPages"
              class="px-3 py-1 rounded bg-blue-500 text-white">
              Next
            </button>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>
  
<script>
export default {
  data() {
    return {
      products: [
        {
          name: "Arif Hidayat",
          groups: "No Groups",
          roles: "Student",
          LastAccess: "1 Hours 30 Minute",
        },
        {
          name: "Arif Hidayat",
          groups: "No Groups",
          roles: "Student",
          LastAccess: "1 Hours 30 Minute",
        },
        {
          name: "Arif Hidayat",
          groups: "No Groups",
          roles: "Student",
          LastAccess: "1 Hours 30 Minute",
        },
        {
          name: "Arif Hidayat",
          groups: "No Groups",
          roles: "Student",
          LastAccess: "1 Hours 30 Minute",
        },
        {
          name: "Arif Hidayat",
          groups: "No Groups",
          roles: "Student",
          LastAccess: "1 Hours 30 Minute",
        },
        {
          name: "Arif Hidayat",
          groups: "No Groups",
          roles: "Student",
          LastAccess: "1 Hours 30 Minute",
        },
        // Daftar produk lainnya di sini
      ],
      itemsPerPage: 5, // Jumlah item per halaman
      currentPage: 1, // Halaman saat ini
    };
  },
  computed: {
    // Menghitung jumlah halaman berdasarkan jumlah item per halaman dan total produk
    totalPages() {
      return Math.ceil(this.products.length / this.itemsPerPage);
    },
    // Data yang ditampilkan berdasarkan halaman saat ini
    paginatedProducts() {
      const startIndex = (this.currentPage - 1) * this.itemsPerPage;
      const endIndex = startIndex + this.itemsPerPage;
      return this.products.slice(startIndex, endIndex);
    },
  },
  methods: {
    // Pindah ke halaman sebelumnya
    prevPage() {
      if (this.currentPage > 1) {
        this.currentPage--;
      }
    },
    // Pindah ke halaman berikutnya
    nextPage() {
      if (this.currentPage < this.totalPages) {
        this.currentPage++;
      }
    },
    // Pindah ke halaman tertentu
    gotoPage(page) {
      this.currentPage = page;
    },
  },
};
</script>
  
<style>
#main{
  height: 1000px;
}
</style>
  