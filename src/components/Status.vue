<script>
export default {
  props: {
    discord_status: String
  }
}
</script>

<template>
  <div class="flex items-center">
    <div v-if="discord_status === 'idle'" class="flex w-4 h-4 ">
      <div class="relative inline-flex w-4 h-4 bg-yellow-400 rounded-full"/>
    </div>
    <div v-else-if="discord_status === 'dnd'" class="flex w-4 h-4 ">
      <div class="relative inline-flex w-4 h-4 bg-red-400 rounded-full"/>
    </div>
    <div v-else-if="discord_status === 'offline'" class="flex w-4 h-4 ">
      <div class="relative inline-flex w-4 h-4 bg-neutral-400 rounded-full"/>
    </div>
    <div v-else class="flex w-4 h-4 ">
      <div class="animate-ping absolute inline-flex w-4 h-4 bg-green-400 rounded-full"/>
      <div class="relative inline-flex w-4 h-4 bg-green-400 rounded-full"/>
    </div>
    <div class="px-1" />
    <p class="uppercase">
      {{discord_status}}
    </p>
  </div>
</template>