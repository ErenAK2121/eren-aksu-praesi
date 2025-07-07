<template>
  <div class="main-card">
    <slot />
  </div>
</template>

<script>
export default {
  name: 'MainCard'
};
</script>

<style scoped>
.main-card {
  background-color: #ffffff;
  border-radius: 12px;
  padding: 24px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.04); /* ganz leichter Shadow */
  transition: box-shadow 0.3s ease;
  border: 1px solid #eaeaea;
  margin: 30px;

}

/* Optional: bei Hover etwas stärkerer Schatten */
.main-card:hover {
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.08);
}
</style>
