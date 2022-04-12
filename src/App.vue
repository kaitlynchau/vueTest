<script>
import Status from './components/Status.vue';

export default {
  components: {
    Status
  },
  data() {
    return {
      discord_status: null
    };
  },
  async created() {
    const response = await fetch("https://api.lanyard.rest/v1/users/721863579787329578");
    const data = await response.json();
    console.log(data);
    this.discord_status = data.data.discord_status;
  }
}
</script>

<template>
  <div class="w-screen h-screen bg-orange-100">
    <div class="flex flex-col h-full justify-center items sm:w-full md:max-w-xl m-auto">
      <div class="bg-orange-50 p-8 rounded-lg h-full w-full md:h-auto md:w-auto">
        <h1 class="text-3xl">
          Kaitlyn Chau
        </h1>
        <Status :discord_status="discord_status" />
        <p class="py-2" />
        <p>hi there!</p>
        <p>
          i am a freshman at NYU studying computer science. my website is still a work in progress, but I hope we can keep in touch:
        </p>
        <p class="py-2" />
        <a class="text-blue-500 hover:text-blue-300 transition" href="mailto:kaitlyn.chau@nyu.edu">
          email me here!
        </a>
      </div>
    </div>
  </div>
</template>

