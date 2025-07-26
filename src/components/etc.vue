<template>
  <section class="etc-section">
    <div class="team-bg">
      <div class="container">
        <div class="team-section">
          <h2 class="team-section-title">Our team</h2>
          <p class="team-section-desc">
            consists of completely different people who are united by a common
            desire - to help
          </p>
          <div class="team-list">
            <div class="team-card" v-for="member in team" :key="member.name">
              <div class="team-avatar">
                <img :src="member.img" :alt="member.name" v-if="member.img" />
                <div v-else class="avatar-placeholder">
                  {{ member.initials }}
                </div>
              </div>
              <div class="team-info">
                <div class="team-name">{{ member.name }}</div>
                <div class="team-role">{{ member.role }}</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="citizens-bg">
      <div class="container">
        <div class="citizens-section">
          <h2 class="citizens-section-title">Socially active citizens</h2>
          <p class="citizens-section-desc">support us</p>
          <div class="citizens-list">
            <div
              class="citizens-card"
              v-for="member in citizens"
              :key="member.name"
            >
              <div class="citizens-avatar">
                <img :src="member.img" :alt="member.name" v-if="member.img" />
                <div v-else class="avatar-placeholder">
                  {{ member.initials }}
                </div>
              </div>
              <div class="citizens-info">
                <div class="citizens-name">{{ member.name }}</div>
                <div class="citizens-role">{{ member.role }}</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="partners-bg">
      <div class="container">
        <div class="partners-section">
          <h2 class="partners-section-title">Our partners</h2>
          <p class="partners-section-desc">
            are take care of our fund and help us with many questions
          </p>
          <div class="partners-list">
            <div
              class="partner-logo"
              v-for="partner in partners"
              :key="partner.alt"
            >
              <img :src="partner.img" :alt="partner.alt" />
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import { gsap } from "gsap";

import { ScrollTrigger } from "gsap/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);

export default {
  name: "AppEtc",
  data() {
    return {
      team: [
        {
          name: "Daryna Deriy",
          role: "Chairman of the Board",
          img: require("../assets/images/team-1.jpg"),
          initials: "DD",
        },
        {
          name: "Polina Snisarenko-Kulchytska",
          role: "Curator of the Foundation",
          img: require("../assets/images/team-2.jpg"),
          initials: "PS",
        },
        {
          name: "Bohdan Kulchytsky",
          role: "Executive Manager",
          img: require("../assets/images/team-3.jpg"),
          initials: "BK",
        },
        {
          name: "Mykhaylo Deriy",
          role: "Operation Manager",
          img: require("../assets/images/team-4.jpg"),
          initials: "MD",
        },
        {
          name: "Ksenia Nikishina",
          role: "Office manager",
          img: require("../assets/images/team-5.jpg"),
          initials: "KN",
        },
        {
          name: "Anna Andriychuk",
          role: "SMM-manager",
          img: require("../assets/images/team-6.jpg"),
          initials: "AA",
        },
        {
          name: "Anastasia Kovalchuk",
          role: "Director",
          img: require("../assets/images/team-7.jpg"),
          initials: "AK",
        },
        {
          name: "Basil Gloo",
          role: "Web Developer",
          img: require("../assets/images/team-8.png"),
          initials: "BG",
        },
        {
          name: "Lina Yakobchuk",
          role: "Designer",
          img: require("../assets/images/team-9.jpg"),
          initials: "LY",
        },
        {
          name: "Anastasia Yevchenko",
          role: "Translator",
          img: require("../assets/images/team-10.jpg"),
          initials: "AY",
        },
        {
          name: "Office Manager",
          role: "open vacancy",
          img: require("../assets/images/6265332e63b917130ca8d702_isa-logo-dog-clean.svg"),
          initials: "AY",
        },
        {
          name: "SEO Specialist",
          role: "open vacancy",
          img: require("../assets/images/6265332e63b917130ca8d702_isa-logo-dog-clean.svg"),
          initials: "AY",
        },
      ],
      citizens: [
        {
          name: "Oleksiy Tritenko",
          role: "theater and film actor",
          img: require("../assets/images/citizen-1.jpg"),
          initials: "OT",
        },
        {
          name: "Stanislav Boklan",
          role: "People's Artist of Ukraine",
          img: require("../assets/images/citizen-2.jpg"),
          initials: "SB",
        },
        {
          name: "Alexander Rudinsky",
          role: "theater and film actor",
          img: require("../assets/images/citizen-3.jpg"),
          initials: "AR",
        },
        {
          name: "Oksana Zhdanova",
          role: "theater and film actress",
          img: require("../assets/images/citizen-4.jpg"),
          initials: "OZ",
        },
        {
          name: "Natalka Denisenko",
          role: "theater and film actress",
          img: require("../assets/images/citizen-5.jpg"),
          initials: "ND",
        },
        {
          name: "Maksym Samchyk",
          role: "theater and film actor",
          img: require("../assets/images/citizen-6.jpg"),
          initials: "MS",
        },
        {
          name: "Kateryna Vyshneva",
          role: "theater and film actress",
          img: require("../assets/images/citizen-7.jpg"),
          initials: "KV",
        },
        {
          name: "Irma Vitovska",
          role: "Honored Actress of Ukraine",
          img: require("../assets/images/citizen-8.jpg"),
          initials: "IV",
        },
        {
          name: "Igor Portyanko",
          role: "actor of theater and cinema",
          img: require("../assets/images/citizen-9.jpg"),
          initials: "IP",
        },
        {
          name: "Dmytro Surzhikov",
          role: "Honored Artist of Ukraine",
          img: require("../assets/images/citizen-10.jpg"),
          initials: "DS",
        },
        {
          name: "Daria Barihashvili",
          role: "theater and film actress",
          img: require("../assets/images/citizen-11.jpg"),
          initials: "DB",
        },
        {
          name: "Vera Kobzar",
          role: "theater and film actress",
          img: require("../assets/images/citizen-12.jpg"),
          initials: "VZ",
        },
        {
          name: "Andriy Fedynchyk",
          role: "theater and film actor",
          img: require("../assets/images/citizen-13.jpg"),
          initials: "AF",
        },
        {
          name: "Anastasia Nesterenko",
          role: "theater and film actress",
          img: require("../assets/images/citizen-14.jpg"),
          initials: "AN",
        },
      ],
      partners: [
        {
          img: require("../assets/images/partner-1.jpg"),
          alt: "Logo-adviRES",
        },
        {
          img: require("../assets/images/partner-2.png"),
          alt: "ovid-wind-logo",
        },
        {
          img: require("../assets/images/partner-3.png"),
          alt: "TBS Industry",
        },
        {
          img: require("../assets/images/partner-4.png"),
          alt: "accurl",
        },
        {
          img: require("../assets/images/partner-5.png"),
          alt: "Laudis",
        },
        {
          img: require("../assets/images/partner-6.jpeg"),
          alt: "kickbite",
        },
      ],
    };
  },
  mounted() {
    this.$nextTick(() => {
      gsap.fromTo(
        ".team-card",
        { opacity: 0, y: 60 },
        {
          opacity: 1,
          y: 0,
          duration: 0.3,
          stagger: 0.18,
          ease: "power2.out",
          scrollTrigger: {
            trigger: ".team-list",
            start: "top 80%",
            end: "bottom 20%",
            toggleActions: "play reverse play reverse",
          },
        }
      );
      gsap.fromTo(
        ".citizens-card",
        { opacity: 0, y: 60 },
        {
          opacity: 1,
          y: 0,
          duration: 0.3,
          stagger: 0.15,
          ease: "power2.out",
          scrollTrigger: {
            trigger: ".citizens-list",
            start: "top 80%",
            end: "bottom 20%",
            toggleActions: "play reverse play reverse",
          },
        }
      );
      gsap.fromTo(
        ".partner-logo",
        { opacity: 0, y: 60 },
        {
          opacity: 1,
          y: 0,
          duration: 0.3,
          stagger: 0.12,
          ease: "power2.out",
          scrollTrigger: {
            trigger: ".partners-list",
            start: "top 80%",
            end: "bottom 20%",
            toggleActions: "play reverse play reverse",
          },
        }
      );
    });
  },
};
</script>

<style scoped>
.etc-section {
  width: 100%;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
  position: relative;
  z-index: 2;
}

.team-bg {
  width: 100%;
  padding: 4rem 0;
  height: 100%;
  background: #fff;
}

.team-section-title {
  font-family: "Inter", "Arial", sans-serif;
  font-size: 3rem;
  font-weight: 700;
  color: #111;
  margin-bottom: 2rem;
  text-align: left;
  line-height: 1.1;
}

.team-section-desc {
  font-family: "Inter", "Arial", sans-serif;
  font-size: 2rem;
  font-weight: 400;
  color: #111;
  text-align: left;
  line-height: 1.4;
  margin-bottom: 3rem;
  max-width: 900px;
}

.team-section {
  margin-bottom: 5rem;
}
.team-list {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 2rem;
  justify-items: stretch;
  align-items: stretch;
  margin-top: 2.5rem;
}

.team-card {
  background: #fff700;
  border: 3px solid #111;
  border-radius: 0;
  box-shadow: none;
  padding: 2rem 1.5rem;
  min-width: 0;
  max-width: none;
  width: 100%;
  min-height: 400px;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-start;
  transition: transform 0.2s, box-shadow 0.2s;
  text-align: center;
}
.team-card:hover {
  transform: translateY(-6px) scale(1.03);
  box-shadow: 0 8px 32px rgba(44, 62, 80, 0.15);
}
.team-avatar {
  width: 220px;
  height: 220px;
  border-radius: 0;
  background: #e9ecef;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 1.2rem;
  overflow: hidden;
}

.team-avatar img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  filter: grayscale(100%);
  display: block;
}

.team-name {
  font-size: 1.3rem;
  font-weight: 600;
  color: #111;
  margin-top: 1rem;
}

.team-role {
  font-size: 1.1rem;
  color: #111;
  margin-top: 0.5rem;
}

.citizens-bg {
  width: 100%;
  padding: 4rem 0;
  height: 100%;
  background: pink;
}

.citizens-section-title {
  font-family: "Inter", "Arial", sans-serif;
  font-size: 3rem;
  font-weight: 700;
  color: #111;
  margin-bottom: 2rem;
  text-align: left;
  line-height: 1.1;
}

.citizens-section-desc {
  font-family: "Inter", "Arial", sans-serif;
  font-size: 2rem;
  font-weight: 400;
  color: #111;
  text-align: left;
  line-height: 1.4;
  margin-bottom: 3rem;
  max-width: 900px;
}

.citizens-section {
  margin-top: 4rem;
}

.citizens-list {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 2.5rem;
  justify-items: center;
  align-items: start;
  margin-top: 2.5rem;
}

.citizens-card {
  background: none;
  border: none;
  box-shadow: none;
  padding: 0;
  min-width: 0;
  max-width: none;
  width: 100%;
  min-height: unset;
  height: auto;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-start;
  text-align: center;
  transition: none;
  margin: 0 2rem;
}

.citizens-avatar {
  width: 260px;
  height: 260px;
  border-radius: 0;
  background: none;
  margin-bottom: 1.2rem;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
}

.citizens-avatar img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  filter: grayscale(100%);
  display: block;
}

.citizens-name {
  font-size: 1.6rem;
  font-weight: 500;
  color: #111;
  margin-top: 1.2rem;
}

.citizens-role {
  font-size: 1.1rem;
  color: #111;
  margin-top: 0.7rem;
}

.partners-bg {
  width: 100%;
  padding: 4rem 0;
  height: 100%;
  background: #fff;
}

.partners-section-title {
  font-family: "Inter", "Arial", sans-serif;
  font-size: 3rem;
  font-weight: 700;
  color: #111;
  margin-bottom: 2rem;
  text-align: left;
  line-height: 1.1;
}

.partners-section-desc {
  font-family: "Inter", "Arial", sans-serif;
  font-size: 2rem;
  font-weight: 400;
  color: #111;
  text-align: left;
  line-height: 1.4;
  margin-bottom: 3rem;
  max-width: 900px;
}

.partners-section {
  margin-top: 4rem;
}

.partners-list {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: repeat(2, auto);
  gap: 3rem 4rem;
  justify-items: center;
  align-items: center;
  margin-top: 2rem;
  background: none;
  box-shadow: none;
}
.partner-logo {
  background: none;
  border-radius: 0;
  box-shadow: none;
  padding: 0;
  min-width: 0;
  min-height: 0;
  max-width: 100%;
  max-height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: none;
}

.partner-logo img {
  max-width: 260px;
  max-height: 90px;
  width: 100%;
  height: auto;
  object-fit: contain;
  filter: grayscale(100%);
  display: block;
}
.partner-logo:hover {
  transform: translateY(-4px) scale(1.05);
  box-shadow: 0 6px 24px rgba(44, 62, 80, 0.13);
}

/* Responsive Design */
@media (max-width: 1100px) {
  .team-list {
    grid-template-columns: repeat(2, 1fr);
  }
}
@media (max-width: 900px) {
  .team-list,
  .partners-list {
    gap: 1.2rem;
  }
}
@media (max-width: 768px) {
  .etc-section {
    padding: 4rem 0;
  }
  .container {
    padding: 0 1.5rem;
  }
  .section-title {
    font-size: 2rem;
  }
  .team-card {
    padding: 1.2rem 0.7rem;
    min-width: 120px;
    max-width: 160px;
  }
  .partner-logo {
    padding: 0.7rem 1rem;
    min-width: 80px;
    min-height: 40px;
    max-width: 120px;
    max-height: 50px;
  }
}
@media (max-width: 480px) {
  .etc-section {
    padding: 2.5rem 0;
  }
  .container {
    padding: 0 0.5rem;
  }
  .section-title {
    font-size: 1.3rem;
  }
  .team-card {
    padding: 0.7rem 0.3rem;
    min-width: 80px;
    max-width: 100px;
  }
  .partner-logo {
    padding: 0.4rem 0.5rem;
    min-width: 50px;
    min-height: 30px;
    max-width: 70px;
    max-height: 30px;
  }
}
</style>
