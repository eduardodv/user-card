<template>
  <main class="bg-blue-100 w-full min-h-screen p-6 flex items-center justify-center">
    <div class="w-96">
      <UserCard :form="form" />
      <form action="" class="bg-white mt-7 rounded-lg bg-white py-7 px-5 md:px-7">
        <div class="">
          <label
            for="name"
            class="cursor-pointer"
          >Name:</label>
          <input
            id="name"
            v-model="form.name"
            type="text"
            name="name"
            class="w-full block border-2 rounded-xl py-1 px-3"
          >
        </div>
        <div class="mt-3">
          <label
            for="phone"
            class="cursor-pointer"
          >Phone:</label>
          <input
            id="phone"
            v-model="form.phone"
            type="tel"
            name="phone"
            class="w-full block border-2 rounded-xl py-1 px-3"
          >
        </div>
        <div class="mt-3">
          <label
            for="email"
            class="cursor-pointer"
          >E-mail:</label>
          <input
            id="email"
            v-model="form.email"
            type="email"
            name="email"
            class="w-full block border-2 rounded-xl py-1 px-3"
          >
        </div>
        <div class="mt-3">
          <label
            for="age"
            class="cursor-pointer"
          >Age:</label>
          <input
            id="age"
            v-model="form.age"
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
            for="file"
            class="cursor-pointer"
          >Picture:</label>
          <input
            id="file"
            type="file"
            name="file"
            class="w-full block border-2 rounded-xl py-1 px-3"
          >
        </div>
      </form>
    </div>
  </main>
</template>

<script>
export default {
  name: 'IndexPage',
  data () {
    return {
      form: {
        name: null,
        phone: null,
        email: null,
        age: null,
        file: null
      }
    }
  }
}
</script>
