<template>
  <div class="min-h-screen flex justify-center items-center">
    <div class="lg:w-1/3 md:2/3">
      <div class="block p-6 rounded-lg shadow-lg bg-white max-w-sm">
        <form @submit.prevent="userLogin">
          <div class="form-group mb-6">
            <label
              for="email"
              class="form-label inline-block mb-2 text-gray-700"
              >Email address</label
            >
            <input
              v-model="login.email"
              type="email"
              class="form-control block w-full px-3 py-1.5 text-base font-normal text-gray-700 bg-white bg-clip-padding border border-solid border-gray-300 rounded transition ease-in-out m-0 focus:text-gray-700 focus:bg-white focus:border-blue-600 focus:outline-none"
              id="email"
              name="email"
              aria-describedby="emailHelp"
              placeholder="Enter email"
              required
            />
          </div>
          <div class="form-group mb-6">
            <label
              for="password"
              class="form-label inline-block mb-2 text-gray-700"
              >Password</label
            >
            <input
              v-model="login.password"
              type="password"
              class="form-control block w-full px-3 py-1.5 text-base font-normal text-gray-700 bg-white bg-clip-padding border border-solid border-gray-300 rounded transition ease-in-out m-0 focus:text-gray-700 focus:bg-white focus:border-blue-600 focus:outline-none"
              id="password"
              name="password"
              placeholder="Password"
              required
            />
          </div>
          <div class="flex justify-between items-center mb-6">
            <div class="form-group form-check">
              <input
                v-model="login.remember_me"
                type="checkbox"
                class="form-check-input appearance-none h-4 w-4 border border-gray-300 rounded-sm bg-white checked:bg-blue-600 checked:border-blue-600 focus:outline-none transition duration-200 mt-1 align-top bg-no-repeat bg-center bg-contain float-left mr-2 cursor-pointer"
                id="rememberMe"
              />
              <label
                class="form-check-label inline-block text-gray-800"
                for="rememberMe"
                >Remember me</label
              >
            </div>
            <NuxtLink
              :to="{ name: 'forgot-password' }"
              class="text-blue-600 hover:text-blue-700 focus:text-blue-700 transition duration-200 ease-in-out"
              >Forgot password?</NuxtLink
            >
          </div>
          <button
            type="submit"
            class="w-full px-6 py-2.5 bg-blue-600 text-white font-medium text-xs leading-tight uppercase rounded shadow-md hover:bg-blue-700 hover:shadow-lg focus:bg-blue-700 focus:shadow-lg focus:outline-none focus:ring-0 active:bg-blue-800 active:shadow-lg transition duration-150 ease-in-out"
          >
            Sign in
          </button>
          <p class="text-gray-800 mt-6 text-center">
            Not a member?
            <NuxtLink
              :to="{ name: 'register' }"
              class="text-blue-600 hover:text-blue-700 focus:text-blue-700 transition duration-200 ease-in-out"
              >Register</NuxtLink
            >
          </p>
        </form>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "Register",

  data() {
    return {
      login: {
        email: "",
        password: "",
      },
    };
  },
  methods: {
    async userLogin() {
      try {
        let response = await this.$auth.loginWith("local", {
          data: this.login,
        });
        this.$toast.success("Successfully authenticated");
        console.log(response);
        this.$router.push({ name: "dashboard" });
      } catch (err) {
        this.$toast.error(err.response.data.message);
        console.log({
          error: err.response,
        });
      }
    },
  },
});
</script>
