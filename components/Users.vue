<template>
  <div class="grid grid-cols-4 gap-3">
    <div v-for="user in users" :key="user.id" class="items-center pb-10">
      <div
        class="col-span-1 p-3 bg-white rounded-lg border border-gray-200 shadow-md dark:bg-gray-800 dark:border-gray-700"
      >
        <img
          class="mb-3 w-24 h-24 rounded-full shadow-lg"
          :src="user.avatar"
          alt="Bonnie image"
        />
        <h5 class="mb-1 text-xl font-medium text-gray-900 dark:text-white">
          {{ user.name }}
        </h5>
        <span class="text-sm text-gray-500 dark:text-gray-400">{{
          user.phone
        }}</span>
        <div class="flex mt-4 space-x-3 lg:mt-6">
          <a
            href="#"
            class="inline-flex items-center py-2 px-4 text-sm font-medium text-center text-white bg-blue-700 rounded-lg hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800"
            >Add friend</a
          >
          <a
            href="#"
            class="inline-flex items-center py-2 px-4 text-sm font-medium text-center text-gray-900 bg-white rounded-lg border border-gray-300 hover:bg-gray-100 focus:ring-4 focus:outline-none focus:ring-gray-200 dark:bg-gray-800 dark:text-white dark:border-gray-600 dark:hover:bg-gray-700 dark:hover:border-gray-700 dark:focus:ring-gray-700"
            >Message</a
          >
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      users: null,
    };
  },
  async created() {
    const res = await this.$axios.get(
      "https://62a7032797b6156bff84ef49.mockapi.io/api/users"
    );
    this.users = res.data;
    console.log(this.users);
  },
};
</script>

<style></style>
