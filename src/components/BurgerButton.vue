<template>
  <button class="burger" @click="$emit('toggle')">
    <svg viewBox="0 0 24 24" fill="none" class="burger-icon" xmlns="http://www.w3.org/2000/svg">
      <path
        fill-rule="evenodd"
        clip-rule="evenodd"
        d="M4 5C3.44772 5 3 5.44772 3 6C3 6.55228 3.44772 7 4 7H20C20.5523 7 21 6.55228 21 6C21 5.44772 20.5523 5 20 5H4ZM7 12C7 11.4477 7.44772 11 8 11H20C20.5523 11 21 11.4477 21 12C21 12.5523 20.5523 13 20 13H8C7.44772 13 7 12.5523 7 12ZM13 18C13 17.4477 13.4477 17 14 17H20C20.5523 17 21 17.4477 21 18C21 18.5523 20.5523 19 20 19H14C13.4477 19 13 18.5523 13 18Z"
        fill="currentColor"
      />
    </svg>
  </button>
</template>

<script>
export default {
  name: 'BurgerButton'
};
</script>

<style scoped>
.burger {
  background: none;
  border: none;
  cursor: pointer;
  padding: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.burger-icon {
  width: 32px;
  height: 32px;
  color: white;
  transition: color 0.2s ease-in-out;
}

.burger:hover .burger-icon {
  color: #00a859; /* Deloitte-Grün */
}
</style>
