<template>
  <footer class="footer-section">
    <div class="container">
      <div class="footer-content">
        <div class="footer-left">
          <h2 class="footer-title">Contact us</h2>
          <div class="footer-address">Kyiv, Ukraine</div>
          <div class="footer-email">mail@isa.co.ua</div>
          <div class="footer-social">
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
        <div class="footer-right">
          <img
            src="@/assets/images/62647f9fbe07235ba9b28d67_star-white-with-animals.svg"
            alt="Footer Illustration"
            class="footer-illustration"
          />
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
import { gsap } from "gsap";

import { ScrollTrigger } from "gsap/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);

export default {
  name: "AppFooter",
  mounted() {
    this.$nextTick(() => {
      gsap.utils.toArray(".footer-section").forEach((section) => {
        gsap.fromTo(
          section,
          { opacity: 0, y: 60 },
          {
            opacity: 1,
            y: 0,
            duration: 1,
            ease: "power2.out",
            scrollTrigger: {
              trigger: section,
              start: "top 80%",
              end: "bottom 20%",
              toggleActions: "play reverse play reverse",
              markers: false,
            },
          }
        );
      });
    });
  },
};
</script>

<style scoped>
.footer-section {
  width: 100%;
  background: #2ecc40;
  color: #111;
  padding: 5rem 0 2rem 0;
  position: relative;
}

.footer-content {
  max-width: 1400px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 2rem;
  padding: 0 2rem;
}

.footer-left {
  flex: 1;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.footer-title {
  font-size: 4rem;
  font-weight: 700;
  margin-bottom: 1.5rem;
}

.footer-address,
.footer-email {
  font-size: 2.2rem;
  margin-bottom: 0.7rem;
}

.footer-social {
  margin-top: 2.2rem;
  display: flex;
  gap: 2rem;
}

.footer-social .social-icon img {
  width: 2.8rem;
  height: 2.8rem;
}

.footer-right {
  flex: 1;
  display: flex;
  justify-content: flex-end;
  align-items: center;
}

.footer-illustration {
  max-width: 400px;
  width: 100%;
  height: auto;
}

@media (max-width: 900px) {
  .footer-content {
    flex-direction: column;
    align-items: flex-start;
    gap: 2.5rem;
  }
  .footer-right {
    justify-content: flex-start;
    margin-top: 2rem;
  }
  .footer-title {
    font-size: 2.5rem;
  }
  .footer-address,
  .footer-email {
    font-size: 1.3rem;
  }
  .footer-social .social-icon img {
    width: 2rem;
    height: 2rem;
  }
  .footer-illustration {
    max-width: 220px;
  }
}
</style>
