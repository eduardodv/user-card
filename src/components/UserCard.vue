<template>
  <div>
    <div class="relative min-h-480 text-center p-5 w-full bg-gradient-to-r from-green-300 to-blue-500 rounded-lg overflow-hidden shadow-lg">
      <button class="dots absolute top-4 right-5">
        <span class="block w-1.5 h-1.5 rounded-full my-1 bg-white transition ease-in-out duration-300" />
        <span class="block w-1.5 h-1.5 rounded-full my-1 bg-white transition ease-in-out duration-300 delay-100" />
        <span class="block w-1.5 h-1.5 rounded-full my-1 bg-white transition ease-in-out duration-300 delay-200" />
      </button>
      <div class=" w-32 h-32 rounded-full m-auto overflow-hidden">
        <img
          src="/images/default-user.jpg"
          alt="Image default user"
          class="object-cover object-top w-full h-full"
        >
      </div>
      <div class="capitalize mt-3">
        <div class="bg-white inline-block py-0.5 px-3 rounded-lg min-h-max">
          <b>{{ form.name ? form.name : 'Jhon Doe' }}{{ form.age ? `, ${form.age}` : '' }}</b>
        </div>
      </div>
      <div class="mt-6">
        <a
          :href="`tel:${form.phone}`"
          class="text-white inline-block hover:underline"
        >
          {{ form.phone ? form.phone : '(42) 9 9999-9999' }}
        </a>
      </div>
      <div class="">
        <a
          :href="`mailto:${form.email}`"
          class="text-white inline-block hover:underline"
        >
          {{ form.email ? form.email : 'email@email.com' }}
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'UserComponent',
  props: {
    form: {
      type: Object,
      default () {
        return {}
      }
    }
  }
}
</script>

<style>
  .dots:hover span {
    transform: scale(1.3);
  }
</style>
