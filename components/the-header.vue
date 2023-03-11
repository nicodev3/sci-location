<template>
  <header class="py-5 bg-violet-600 font-bold text-lg text-white px-5">
    <nav class="container mx-auto">
      <ul class="flex gap-5 justify-end">
        <li class="mr-auto">
          <nuxt-link to="/">Home</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/">Le cabinet</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/contact">Contact</nuxt-link>
        </li>
      </ul>
    </nav>
  </header>
</template>
<script>
export default {
  name: 'TheHeader'
}
</script>
