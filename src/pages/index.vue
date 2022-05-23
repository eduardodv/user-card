<template>
  <main class="bg-blue-100 w-full min-h-screen p-6 flex items-center justify-center overflow-hidden">
    <div class="w-96 lg:w-full max-w-3xl lg:flex lg:gap-5">
      <UserCard :form="form" />
      <form
        class="lg:order-1 lg:w-1/2 bg-white mt-7 lg:mt-0 rounded-lg bg-white py-7 px-5 md:px-7"
        @submit.prevent="submit"
      >
        <div class="">
          <label
            for="name"
            class="cursor-pointer text-sm mb-1 inline-block"
          >Name:</label>
          <input
            id="name"
            v-model="form.name"
            required
            type="text"
            name="name"
            class="w-full block border-2 rounded-xl py-1 px-3"
          >
        </div>
        <div class="mt-3">
          <label
            for="age"
            class="cursor-pointer text-sm mb-1 inline-block"
          >Age:</label>
          <input
            id="age"
            v-model="form.age"
            v-mask="'###'"
            required
            type="number"
            name="age"
            min="0"
            max="150"
            value="0"
            class="w-full block border-2 rounded-xl py-1 px-3"
          >
        </div>
        <div class="mt-3">
          <label
            for="phone"
            class="cursor-pointer text-sm mb-1 inline-block"
          >Phone:</label>
          <input
            id="phone"
            v-model="form.phone"
            v-mask="['(##) ####-####', '(##) #####-####']"
            required
            type="tel"
            name="phone"
            class="w-full block border-2 rounded-xl py-1 px-3"
          >
        </div>
        <div class="mt-3">
          <label
            for="email"
            class="cursor-pointer text-sm mb-1 inline-block"
          >E-mail:</label>
          <input
            id="email"
            v-model="form.email"
            required
            type="email"
            name="email"
            class="w-full block border-2 rounded-xl py-1 px-3"
          >
        </div>
        <div class="mt-5 relative">
          <label
            for="file"
            role="button"
            class="cursor-pointer text-sm mb-1 block border-dashed border-2 hover:border-blue-500 transition ease-in-out duration-200 py-5 px-4 text-center"
          >
            {{ form.file ? form.file.name : 'UPLOAD IMAGE' }}
          </label>
          <input
            id="file"
            required
            type="file"
            name="file"
            class="opacity-0 absolute top-0 left-0"
            accept="image/*"
            @change="filePicture"
          >
        </div>
        <div class="mt-5 text-center">
          <button
            type="submit"
            class="bg-blue-500 text-white font-bold uppercase px-10 py-2 rounded-full hover:bg-green-500 transition ease-in-out duration-300"
          >
            Send
          </button>
        </div>
      </form>
    </div>
  </main>
</template>

<script>
import { mask } from 'vue-the-mask'

export default {
  name: 'IndexPage',

  directives: { mask },

  data () {
    return {
      customFile: null,
      form: {
        name: null,
        age: null,
        phone: null,
        email: null,
        file: null
      }
    }
  },

  methods: {
    filePicture (event) {
      const file = event.target.files[0]
      if (file) {
        this.form.file = {
          name: file.name,
          url: URL.createObjectURL(file)
        }
      }
    },

    submit () {
      console.log(this.form)
    }

  }
}
</script>
