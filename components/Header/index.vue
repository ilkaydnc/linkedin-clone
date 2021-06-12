<script>
import Search from '../Search.vue'

export default {
  components: { Search },
  name: 'Header',
}
</script>

<template>
  <header class="header">
    <div class="container header-inner">
      <NuxtLink to="/">
        <img
          class="header-icon"
          src="@/assets/linkedin-icon.png"
          alt="Linkedin"
        />
      </NuxtLink>
      <search />
    </div>
  </header>
</template>

<style scoped>
.header {
  background-color: #0b66c3;
}

.header-inner {
  display: flex;
  gap: 16px;
  padding-top: 16px;
  padding-bottom: 16px;
}

.header-icon {
  width: 42px;
  height: 42px;
}

.header-inner a {
  display: inline-flex;
}
</style>