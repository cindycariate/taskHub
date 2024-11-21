<template>
  <div class="auth-background">
    <slot></slot>
  </div>
</template>

<style scoped>
.auth-background {
  background-image: url('@/assets/img/bg.jpg');
  background-size: cover;
  background-position: center;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 20px;
}
</style>
