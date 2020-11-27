<template>
  <div class="container mx-auto mt-8">
    <h1 class="font-bold text-xl text-center">Products</h1>
    <button
      class="text-sm bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-2 rounded-full mb-4"
      @click="showMountains"
    >
      Refresh
    </button>
    <LazyProductCard v-if="show" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      show: false,
    }
  },
  methods: {
    showMountains() {
      this.show = true
    },
  },
}
</script>

<style lang="postcss">
img {
  height: 120px;
}
</style>
