<template>
  <header class="header">
    <div class="header-container">
      <div class="hero-content">
        <div class="logo-section">
          <transition name="slide-down" mode="out-in">
            <img
              :src="logoList[currentLogo]"
              alt="ISA Logo"
              class="logo"
              :key="currentLogo"
            />
          </transition>
        </div>
        <div class="brand-section">
          <div class="brand-text">
            <h1 class="main-title">
              Innovative<br />
              Solutions<br />
              for<br />
              Animals
            </h1>
          </div>
        </div>
      </div>
      <div class="brand-footer">
        <div class="subtitle-section">
          <p class="subtitle">charity organization</p>
        </div>
        <div class="social-media">
          <a href="#" class="social-icon">
            <img
              src="../assets/images/6274433d06989d76edcff015_9055867_youtube_bxl.svg"
              alt="YouTube"
            />
          </a>
          <a href="#" class="social-icon">
            <img
              src="../assets/images/6274449bf840c377311f2e08_9055851_instagram_bxl.svg"
              alt="Instagram"
            />
          </a>
          <a href="#" class="social-icon">
            <img
              src="../assets/images/627443d78de17d2c59c8352c_9055795_facebook_bxl.svg"
              alt="Facebook"
            />
          </a>
          <a href="#" class="social-icon">
            <img
              src="../assets/images/6274440c6a0ab7631dce0cd1_9055888_patreon_bxl.svg"
              alt="Patreon"
            />
          </a>
          <a href="#" class="social-icon">
            <img
              src="../assets/images/627443f9ac91b492e4c220ba_9055800_telegram_bxl.svg"
              alt="Telegram"
            />
          </a>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
import { gsap } from "gsap";

export default {
  name: "AppHeader",
  data() {
    return {
      logoList: [
        require("../assets/images/6265332e63b917130ca8d702_isa-logo-dog-clean.svg"),
        require("../assets/images/627fc81139e6f5dca2d02054_isa-logo-cat-clean.svg"),
      ],
      currentLogo: 0,
      intervalId: null,
    };
  },
  mounted() {
    gsap.from(".hero-content", {
      y: 50,
      opacity: 0,
      duration: 1.2,
      ease: "power2.out",
    });
    gsap.from(".social-icon", {
      y: 20,
      opacity: 1,
      duration: 0.8,
      stagger: 0.1,
      ease: "power2.out",
      delay: 0.5,
    });

    this.intervalId = setInterval(() => {
      this.nextLogo();
    }, 2500);
  },
  beforeUnmount() {
    clearInterval(this.intervalId);
  },
  methods: {
    nextLogo() {
      this.currentLogo = (this.currentLogo + 1) % this.logoList.length;
    },
  },
};
</script>

<style scoped>
.slide-down-enter-active,
.slide-down-leave-active {
  transition: all 0.6s cubic-bezier(0.77, 0, 0.175, 1);
}
.slide-down-enter,
.slide-down-leave-to {
  opacity: 0;
  transform: translateY(-80px);
}

.header {
  width: 100%;
  min-height: 100vh;
  background: #ffd700;
  display: flex;
  align-items: center;
  position: relative;
  overflow: hidden;
}

.header-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  position: relative;
  z-index: 2;
  width: 100%;
}

.hero-content {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  gap: 3rem;
  max-width: 900px;
  margin: 0 auto;
}

.logo-section {
  flex-shrink: 0;
  height: 240px;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
}

.logo {
  width: 240px;
  height: 240px;
  filter: brightness(0);
}

.brand-section {
  display: flex;
  flex-direction: column;
  gap: 2rem;
  flex: 1;
}

.brand-text {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.main-title {
  font-size: 3.5rem;
  font-weight: 700;
  line-height: 1.1;
  color: #000000;
  margin: 0;
  text-align: left;
}

.brand-footer {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1.2rem;
  width: 100%;
  margin-top: 2.5rem;
}

.subtitle-section {
  text-align: center;
  margin-bottom: 0;
}

.subtitle {
  font-size: 2.5rem;
  color: #000000;
  margin: 0;
  font-weight: 500;
  text-transform: lowercase;
  letter-spacing: 1px;
}

.social-media {
  margin-top: 0;
  display: flex;
  gap: 1rem;
  align-items: center;
  justify-content: center;
}

.social-icon {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 60px;
  height: 0px;
  background: transparent;
  border-radius: 50%;
  transition: all 0.3s ease;
}

.social-icon:hover {
  transform: translateY(-2px) scale(1.1);
}

.social-icon img {
  width: 46px;
  height: 46px;
  filter: brightness(0);
}

/* Responsive Design */
@media (max-width: 900px) {
  .hero-content {
    gap: 1.5rem;
  }
}
@media (max-width: 768px) {
  .hero-content {
    flex-direction: column;
    align-items: center;
    text-align: center;
    gap: 2rem;
  }
  .main-title {
    font-size: 2.8rem;
    text-align: center;
  }
  .subtitle-section {
    text-align: center;
  }
  .social-media {
    justify-content: center;
  }
  .logo {
    width: 100px;
    height: 100px;
  }
}

@media (max-width: 480px) {
  .header-container {
    padding: 0 1rem;
  }
  .main-title {
    font-size: 2.2rem;
  }
  .logo {
    width: 80px;
    height: 80px;
  }
  .social-icon {
    width: 35px;
    height: 35px;
  }
  .social-icon img {
    width: 20px;
    height: 20px;
  }
}
</style>
