<template>
  <header ref="vantaHeader" class="header">
    <div class="left">
      <div v-if="!isMobile || menuOpen" class="expanded">
        <img
          :src="profilePicture"
          alt="Bewerbungsfoto"
          class="profile-picture"
        />
        <div class="text-content">
          <h1 class="name">{{ name }}</h1>
          <h2 class="title">Wirtschaftsinformatiker (B.Sc.)</h2>
        </div>
      </div>
      <div v-else class="collapsed">
        <h1 class="name">{{ name }}</h1>
      </div>
    </div>

    <button class="burger" @click="menuOpen = !menuOpen" v-if="isMobile">
      ☰
    </button>
  </header>
</template>

<script>
export default {
  name: "Header",
  data() {
    return {
      profilePicture: 'src/assets/eren-aksu-foto.jpeg',
      name: 'Eren Aksu',
      isMobile: false,
      menuOpen: false,
      vantaEffect: null
    }
  },
  mounted() {
    this.checkScreen()
    window.addEventListener('resize', this.checkScreen)

    // VANTA.NET init
    this.vantaEffect = window.VANTA.NET({
      el: this.$refs.vantaHeader,
      mouseControls: true,
      touchControls: true,
      gyroControls: false,
      minHeight: 200.00,
      minWidth: 200.00,
      scale: 1.00,
      scaleMobile: 1.00,
      color: 0x86bc25,
      backgroundColor: 0x000000,
      points: 11.00,
      maxDistance: 17.00,
      spacing: 14.00
    })
  },
  beforeUnmount() {
    window.removeEventListener('resize', this.checkScreen)
    if (this.vantaEffect) this.vantaEffect.destroy()
  },
  methods: {
    checkScreen() {
      this.isMobile = window.innerWidth <= 768
      if (!this.isMobile) {
        this.menuOpen = false
      }
    }
  }
}
</script>

<style scoped>
.header {
  width: 100%;
  height: 200px;
  position: relative;
  color: white;
  display: flex;
  align-items: center;
  padding: 24px;
  padding-top: 0px;
  overflow: hidden;
}
.left {
  display: flex;
  align-items: center;
  flex: 1;
  z-index: 1;
}
.expanded {
  display: flex;
  align-items: center;
  gap: 20px;
  flex-wrap: wrap;
}
.collapsed {
  display: flex;
  align-items: center;
}
.profile-picture {
  width: 150px;
  height: 150px;
  object-fit: cover;
  object-position: top;
  border-radius: 12px;
  border: 2px solid white;
}
.text-content {
  display: flex;
  flex-direction: column;
  padding-left: 30px;
}
.name {
  font-size: 28px;
  font-weight: 700;
  margin: 0;
}
.title {
  font-size: 18px;
  font-weight: 400;
  margin-top: 4px;
  color: #86bc25;
}
.burger {
  z-index: 1;
  background: none;
  border: none;
  font-size: 32px;
  color: white;
}
</style>
