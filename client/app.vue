<template>
  <NuxtLoadingIndicator throttle="0" />
  <Navbar />
  <NuxtPage />
  <Footer />

</template>

<script setup>
const base = 'http://localhost:1337'
const api = await $fetch(`${base}/api/config?populate=*`)
const config = api.data

useHead({
  title: config.title,
  meta: [
    { name: 'description', content: config.desc },
    { name: 'keywords', content: config.keywords },
  ],
  link: [
    { rel: 'icon', type: 'image/x-icon', href: base + config.favicon.url }
  ]
})

</script>

<style>

/* * {
  margin: 0px;
} */


html,
body,
#__nuxt {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
}

body {
  margin: 0;
  background: url("https://i.pinimg.com/originals/3c/2b/ea/3c2bea01b4b02c0387fd99d330ae84eb.jpg");
  background-blend-mode: color;
}

main {
  flex: 1 1 auto;
}
</style>
