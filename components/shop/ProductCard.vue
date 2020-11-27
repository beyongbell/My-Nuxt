<template>
  <div>
    <p v-if="$fetchState.pending">Fetching mountains...</p>
    <p v-else-if="$fetchState.error">An error occurred :(</p>
    <div
      v-for="mountain in mountains"
      v-else
      :key="mountain.title"
      class="mb-4 flex felx-col text-left md:flex"
    >
      <div class="md:flex-shrink-0">
        <img
          :src="mountain.image"
          :alt="mountain.title"
          class="rounded-lg md:w-56"
        />
      </div>
      <div class="mt-4 md:mt-4 md:ml-6">
        <div class="uppercase tracking-wide text-sm text-indigo-600 font-bold">
          {{ mountain.continent }}
        </div>
        <NuxtLink
          :to="mountain.slug"
          class="block mt-1 text-lg leading-tight font-semibold text-gray-900 hover:underline"
        >
          {{ mountain.title }}
        </NuxtLink>
        <p class="mt-2 text-gray-600">{{ mountain.description }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  async fetch() {
    this.mountains = await fetch(
      'https://api.nuxtjs.dev/mountains'
    ).then((res) => res.json())
  },
  data() {
    return {
      mountains: [],
    }
  },
}
</script>

<style lang="postcss">
img {
  height: 120px;
}
</style>
