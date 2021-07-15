<template>
  <section id="homepage">
    <!-- <NuxtLogo /> -->
    <h1 class="text-2xl">Welcome to Our Nuxt Store</h1>
    <p>
      This is a website where I learn about SEO and how to leverage NuxtJS's SSR
      to achieve a better SEO
    </p>

    <h2></h2>
  </section>
</template>

<script>
const SEO_CONTENTS = {
  description:
    "This is a website where I learn about SEO and how to leverage NuxtJS's SSR to achieve a better SEO",
}

export default {
  head() {
    return {
      title: 'Home | Learn Nuxt and Seo',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: SEO_CONTENTS.description,
        },
      ],
    }
  },
}
</script>
