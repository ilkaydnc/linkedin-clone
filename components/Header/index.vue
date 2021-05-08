<script>
export default {
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
    </div>
  </header>
</template>

<style scoped>
.header {
  background-color: #0b66c3;
}

.header-inner {
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