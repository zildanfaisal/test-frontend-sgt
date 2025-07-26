<template>
  <section class="section-2">
    <div class="projects-bg">
      <div class="container">
        <div class="projects-section">
          <h2 class="projects-section-title">Our projects</h2>
          <p class="projects-section-desc">
            are very different in terms of priority, scale and complexity of
            implementation
          </p>
          <div class="projects-list">
            <div class="project-card project-black">
              <h3 class="project-title">Emergency Aid. WAR 2022.</h3>
              <p class="project-desc">
                providing food and medicine to the shelters and animals which
                lost their homes and families due to the war
              </p>
            </div>
            <div class="project-card project-green">
              <h3 class="project-title">Non-commercial feed line</h3>
              <p class="project-desc">
                construction of industrial production base where food for
                shelters will be produced on a free basis
              </p>
            </div>
            <div class="project-card project-orange">
              <h3 class="project-title">Education and Control</h3>
              <p class="project-desc">
                lectures on communication, organisation and coordination of
                processes, control over the use of aid
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="help-bg">
      <div class="container">
        <div class="help-section">
          <h2 class="help-section-title">We want to help</h2>
          <p class="help-section-desc">
            homeless packs, volunteers, guardians, overstayers, shelters and
            other organisations
          </p>
          <div class="shelter-list">
            <span class="shelter">Shelter of Victoria Bulbyna</span>
            <span class="shelter">City of faithful hearts</span>
            <span class="shelter">Shelter of Natalia Tymoshenko</span>
            <span class="shelter">Shelter of Jeanne Sass</span>
            <span class="shelter">Shelter of Victoria Bondarenko</span>
            <span class="shelter">Sterilization center</span>
            <span class="shelter">Zoo chance</span>
            <span class="shelter">Save lives</span>
            <span class="shelter"
              >City Center for the Treatment of Animals</span
            >
            <span class="shelter"
              >Society for the Protection of Animals in Sumy</span
            >
            <span class="shelter">The right to life</span>
            <span class="shelter">4 paws</span>
            <span class="shelter">The kingdom of cats</span>
            <span class="shelter">Zvir</span>
            <span class="shelter">Mercy</span>
            <span class="shelter">Happy dog</span>
            <span class="shelter">Give me a paw, friend</span>
            <span class="shelter">Friend</span>
            <span class="shelter">Hope</span>
            <span class="shelter">We are for the right to life</span>
            <span class="shelter">Planeta</span>
            <span class="shelter">Second Life</span>
            <span class="shelter">Happy shore</span>
            <span class="shelter">Retrieverteam</span>
            <span class="shelter">Shelter of Irina Dobrolyubova</span>
            <span class="shelter">Matilda</span>
            <span class="shelter">Life</span>
            <span class="shelter">Second chance</span>
            <span class="shelter">SOS</span>
            <span class="shelter">Best friends</span>
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
  name: "AppSection1",
  mounted() {
    this.$nextTick(() => {
      gsap.fromTo(
        ".project-card",
        { opacity: 0, y: 60 },
        {
          opacity: 1,
          y: 0,
          duration: 0.5,
          stagger: 0.25,
          ease: "power2.out",
          scrollTrigger: {
            trigger: ".projects-list",
            start: "top 80%",
            end: "bottom 20%",
            toggleActions: "play reverse play reverse",
          },
        }
      );
      gsap.fromTo(
        ".shelter",
        { opacity: 0, y: 60 },
        {
          opacity: 1,
          y: 0,
          duration: 0.3,
          stagger: 0.12,
          ease: "power2.out",
          scrollTrigger: {
            trigger: ".shelter-list",
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
.section-2 {
  width: 100%;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

.projects-bg {
  width: 100%;
  padding: 4rem 0;
  height: 100%;
  background: #4da3ff;
}

.help-bg {
  width: 100%;
  padding: 4rem 0;
  height: 100%;
  background: yellow;
}

.projects-section {
  margin-bottom: 5rem;
}

.projects-section-title {
  font-family: "Inter", "Arial", sans-serif;
  font-size: 3rem;
  font-weight: 700;
  color: #fff;
  margin-bottom: 2rem;
  text-align: left;
  line-height: 1.1;
}

.projects-section-desc {
  font-family: "Inter", "Arial", sans-serif;
  font-size: 2rem;
  font-weight: 400;
  color: #fff;
  text-align: left;
  line-height: 1.4;
  margin-bottom: 3rem;
  max-width: 900px;
}

.help-section-title {
  font-family: "Inter", "Arial", sans-serif;
  font-size: 3rem;
  font-weight: 700;
  color: #111;
  margin-bottom: 2rem;
  text-align: left;
  line-height: 1.1;
}

.help-section-desc {
  font-family: "Inter", "Arial", sans-serif;
  font-size: 2rem;
  font-weight: 400;
  color: #111;
  text-align: left;
  line-height: 1.4;
  margin-bottom: 3rem;
  max-width: 900px;
}

.projects-list {
  display: flex;
  flex-direction: column;
  gap: 2.5rem;
}

.project-card {
  width: 100%;
  border: 3px solid #fff;
  border-radius: 8px;
  padding: 2.5rem 2rem;
  margin: 0 auto;
  box-sizing: border-box;
  max-width: 1000px;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.project-title {
  font-family: "Inter", "Arial", sans-serif;
  font-size: 2.3rem;
  font-weight: 700;
  margin-bottom: 1.2rem;
  color: #fff;
  text-align: left;
}

.project-desc {
  font-family: "Inter", "Arial", sans-serif;
  font-size: 1.4rem;
  font-weight: 400;
  color: #fff;
  text-align: left;
  line-height: 1.4;
}

.project-black {
  background: #111;
}

.project-green {
  background: #27c33a;
}

.project-orange {
  background: #ff9800;
}

.help-section {
  margin-top: 4rem;
}

.shelter-list {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2rem;
  justify-content: center;
  align-items: center;
  margin-top: 2.5rem;
}
.shelter {
  background: #fff;
  border: 2px solid #111;
  color: #111;
  padding: 2rem 2.5rem;
  border-radius: 8px;
  font-size: 1.3rem;
  font-weight: 500;
  box-shadow: 0 2px 8px rgba(44, 62, 80, 0.08);
  transition: background 0.2s, color 0.2s, transform 0.2s;
  cursor: pointer;
  text-align: center;
  min-width: 300px;
  min-height: 140px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.shelter:hover {
  background: #ffe066;
  transform: translateY(-4px) scale(1.04);
}

@media (max-width: 900px) {
  .shelter-list {
    grid-template-columns: repeat(2, 1fr);
    gap: 1rem;
  }
  .shelter {
    min-width: 180px;
    min-height: 90px;
    font-size: 1rem;
    padding: 1.2rem 1rem;
  }
  .container {
    max-width: 100%;
    padding: 0 1.2rem;
  }
  .section-title {
    font-size: 2.2rem;
  }
  .section-desc {
    font-size: 1.3rem;
  }
  .project-title {
    font-size: 1.5rem;
  }
  .project-desc {
    font-size: 1rem;
  }
  .project-card {
    padding: 1.5rem 1rem;
  }
}
@media (max-width: 600px) {
  .shelter-list {
    grid-template-columns: 1fr;
    gap: 0.7rem;
  }
  .shelter {
    min-width: 100px;
    min-height: 60px;
    font-size: 0.9rem;
    padding: 0.7rem 0.5rem;
  }
  .section-2 {
    padding: 3rem 0 2rem 0;
  }
  .section-title {
    font-size: 1.5rem;
    margin-bottom: 1.2rem;
  }
  .section-desc {
    font-size: 1rem;
    margin-bottom: 1.5rem;
  }
  .project-title {
    font-size: 1.1rem;
  }
  .project-desc {
    font-size: 0.9rem;
  }
  .project-card {
    padding: 1rem 0.5rem;
  }
}
</style>
