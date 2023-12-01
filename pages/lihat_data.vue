<template>
    <div>
      <h1 class="text-2xl font-bold mb-4">Data yang Diinputkan</h1>
  
      <table class="min-w-full divide-y divide-gray-200 dark:divide-gray-700">
  <thead class="bg-gray-50 dark:bg-gray-800">
    <tr>
      <th scope="col" class="px-6 py-3 text-left text-xs font-medium text-gray-500 dark:text-gray-300 uppercase tracking-wider">***</th>
      <th scope="col" class="px-6 py-3 text-left text-xs font-medium text-gray-500 dark:text-gray-300 uppercase tracking-wider">Data</th>
    </tr>
  </thead>
  <tbody class="bg-white dark:bg-gray-900 divide-y divide-gray-200 dark:divide-gray-700">
    <tr>
      <td class="px-6 py-4 whitespace-nowrap text-sm font-medium text-gray-900 dark:text-white">Nama</td>
      <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500 dark:text-gray-400">{{ formData.first_name }}</td>
    </tr>
    <tr>
      <td class="px-6 py-4 whitespace-nowrap text-sm font-medium text-gray-900 dark:text-white">Perusahaan</td>
      <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500 dark:text-gray-400">{{ formData.company }}</td>
    </tr>
    <tr>
      <td class="px-6 py-4 whitespace-nowrap text-sm font-medium text-gray-900 dark:text-white">No Telepon</td>
      <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500 dark:text-gray-400">{{ formData.phone }}</td>
    </tr>
    <tr>
      <td class="px-6 py-4 whitespace-nowrap text-sm font-medium text-gray-900 dark:text-white">Link Instagram</td>
      <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500 dark:text-gray-400">{{ formData.website }}</td>
    </tr>
    <tr>
      <td class="px-6 py-4 whitespace-nowrap text-sm font-medium text-gray-900 dark:text-white">Email</td>
      <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500 dark:text-gray-400">{{ formData.email }}</td>
    </tr>
  </tbody>
</table>

  
      <button @click="goBack" class="mt-4 text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm w-full sm:w-auto px-5 py-2.5 text-center dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800">Back</button>
    </div>
  </template>
  
  <script>
  export default {
    methods: {
        saveFormData() {
    localStorage.setItem('formData', JSON.stringify(this.formData));
     },
      goBack() {
        this.$router.push('/home');
      },
    },
    data() {
      return {
        formData: JSON.parse(localStorage.getItem('formData')) || {},
      };
    }
  };
  </script>
  
  