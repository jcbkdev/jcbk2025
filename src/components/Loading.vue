<template>
  <div class="loading"></div>
</template>

<style scoped>
.loading {
  display: block;

  border: 6px solid #ffffff00;
  border-top: 6px solid #ffffff;
  border-radius: 50%;
  width: 48px;
  height: 48px;

  animation: spin 2s linear infinite;
}

@keyframes spin {
  from {
    rotate: 0deg;
  }
  to {
    rotate: 360deg;
  }
}
</style>
