<template>
  <section class="section-1">
    <div class="container">
      <div class="we-are-section">
        <h2 class="section-title">We are</h2>
        <p class="section-description">
          team of like-minded people, socially active companies, media
          personalities, volunteers who help low-income shelters and foster
          carers to support homeless animals.
        </p>
      </div>
      <div class="primary-goal-section">
        <h2 class="section-title">Our primary goal</h2>
        <p class="section-description">
          is to provide animals with the most necessary things – food, medicine,
          and urgent needs for the livelihood of shelters. We believe in our
          power and the power of conscious citizens who care about the
          environment and their health, who understand the importance of helping
          each other, especially our little friends. Growth begins with your
          care for your loved ones. Animals are one of the closest creatures to
          humans who remain with us throughout our lives. We all know the
          healing power of warmth, grace, and big loving eyes.
        </p>
      </div>
      <div class="quote-section">
        <blockquote class="quote">
          <span class="quote-text"
            >"Animals need to have friends. Just like humans."</span
          ><br />
          <span class="quote-author"
            >– James Herriot, All Creatures Great and Small</span
          >
        </blockquote>
      </div>
      <div class="cta-section">
        <p class="cta-text">
          Who else if not we should support our younger brothers, especially in
          difficult times? Let's be friends!
        </p>
      </div>
      <div class="video-section">
        <div class="video-responsive">
          <iframe
            width="560"
            height="315"
            src="https://www.youtube.com/embed/5Wk1rp99B7o?si=0sLlYJ3Jupj7W8Ys"
            title="YouTube video player"
            frameborder="0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
            referrerpolicy="strict-origin-when-cross-origin"
            allowfullscreen
          ></iframe>
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
      gsap.utils.toArray(".section-1").forEach((section) => {
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
.section-1 {
  width: 100%;
  background: #fff;
  padding: 6rem 0 4rem 0;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

.we-are-section,
.primary-goal-section {
  margin-bottom: 4rem;
}

.section-title {
  font-family: "Inter", "Arial", sans-serif;
  font-size: 3rem;
  font-weight: 700;
  color: #111;
  margin-bottom: 2rem;
  text-align: left;
  line-height: 1.1;
}

.section-description {
  font-family: "Inter", "Arial", sans-serif;
  font-size: 2rem;
  font-weight: 400;
  color: #111;
  text-align: left;
  line-height: 1.4;
  max-width: 900px;
}

.quote-section {
  margin-bottom: 3rem;
}

.quote {
  font-family: "Inter", "Arial", sans-serif;
  font-size: 2rem;
  font-style: italic;
  color: #111;
  border-left: 6px solid #f48fb1;
  padding-left: 1.2rem;
  margin: 0;
  background: none;
}

.quote-author {
  font-size: 1.3rem;
  font-style: italic;
  color: #222;
}

.cta-section {
  margin-bottom: 3rem;
}

.cta-text {
  font-family: "Inter", "Arial", sans-serif;
  font-size: 2rem;
  font-weight: 500;
  color: #111;
  text-align: left;
  line-height: 1.3;
}

.video-section {
  margin-top: 2.5rem;
}

.video-responsive {
  position: relative;
  padding-bottom: 56.25%;
  height: 0;
  overflow: hidden;
  max-width: 900px;
  margin: 0 auto;
  border-radius: 12px;
  box-shadow: 0 2px 16px rgba(0, 0, 0, 0.08);
}

.video-responsive iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border: 0;
}

@media (max-width: 900px) {
  .container {
    max-width: 100%;
    padding: 0 1.2rem;
  }
  .section-title {
    font-size: 2.2rem;
  }
  .section-description,
  .cta-text,
  .quote {
    font-size: 1.3rem;
  }
  .quote-author {
    font-size: 1.1rem;
  }
}
@media (max-width: 600px) {
  .section-1 {
    padding: 3rem 0 2rem 0;
  }
  .section-title {
    font-size: 1.5rem;
    margin-bottom: 1.2rem;
  }
  .section-description,
  .cta-text,
  .quote {
    font-size: 1rem;
  }
  .quote-author {
    font-size: 0.95rem;
  }
  .we-are-section,
  .primary-goal-section {
    margin-bottom: 2rem;
  }
}
</style>
