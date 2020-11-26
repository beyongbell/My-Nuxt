<template>
  <div>
    <div v-if="$nuxt.isOffline">You are offline</div>
    <div v-if="$nuxt.isOnline">You are onLine</div>
    <Nuxt />
  </div>
</template>
