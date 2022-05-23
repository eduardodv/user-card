<template>
  <div id="card" class="lg:flex lg:order-2 lg:w-1/2 transition ease-in-out duration-400 transform hover:skew-y-6">
    <div class="lg:flex lg:items-center lg:justify-center lg:min-h-full relative text-center p-5 w-full bg-gradient-to-r from-green-300 to-blue-500 rounded-lg overflow-hidden shadow-lg">
      <div>
        <button class="dots group absolute top-3 right-2 py-1 px-3">
          <span class="block w-1.5 h-1.5 rounded-full my-1 bg-white transform group-hover:scale-125 transition ease-in-out duration-300" />
          <span class="block w-1.5 h-1.5 rounded-full my-1 bg-white transform group-hover:scale-125 transition ease-in-out duration-300 delay-100" />
          <span class="block w-1.5 h-1.5 rounded-full my-1 bg-white transform group-hover:scale-125 transition ease-in-out duration-300 delay-200" />
        </button>
        <div class=" w-32 h-32 rounded-full m-auto overflow-hidden bg-blue-500">
          <img
            v-if="form.file"
            :src="form.file.url"
            alt="User image"
            class="object-cover object-top w-full h-full"
          >
          <img
            v-else
            src="/images/default-user.jpg"
            alt="Image default user"
            class="object-cover object-top w-full h-full"
          >
        </div>
        <div class="mt-3">
          <div class="bg-white inline-block py-0.5 px-3 rounded-lg min-h-max">
            <b>{{ form.name ? form.name : 'John Doe' }}</b>
            <b>{{ form.age ? `, ${form.age}` : '' }}</b>
          </div>
        </div>
        <div class="mt-6">
          <a
            :href="`tel:${clearnum(form.phone)}`"
            class="text-white text-lg inline-block hover:underline"
          >
            {{ form.phone }}
          </a>
        </div>
        <div class="">
          <a
            :href="`mailto:${form.email}`"
            class="text-white text-lg inline-block hover:underline break-all"
          >
            {{ form.email }}
          </a>
        </div>
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
  },

  methods: {
    clearnum (num) {
      if (num) {
        return num.replace(/[^\d]/g, '')
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
