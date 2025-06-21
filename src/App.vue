<script setup lang="ts">
import TestiminialsCard from './components/TestiminialsCard.vue'
import testimonialsData from '@/data/testimonialsData.json'
</script>

<template>
  <main class="p-main">
    <img class="p-main__quotation-image" src="/images/bg-pattern-quotation.svg" alt="" />
    <TestiminialsCard
      v-for="testimonial in testimonialsData"
      :key="testimonial.id"
      :background="testimonial.background"
      :text-color-black="testimonial.textColorBlack"
      :user-picture="testimonial.userPicture"
      :user-name="testimonial.name"
      :message="testimonial.message"
      :message-details="testimonial.messageDetails"
      :col-span="testimonial.colSpan"
      :row-span="testimonial.rowSpan"
    />
  </main>
  <footer class="p-footer">
    <p class="p-footer__attribution">
      Challenge by
      <a href="https://www.frontendmentor.io?ref=challenge" target="_blank">Frontend Mentor</a>.
      Coded by
      <a href="https://github.com/mickael-o3o/testimonials-grid-section.git" target="_blank"
        >mickael-o3o</a
      >.
    </p>
  </footer>
</template>

<style scoped lang="scss">
.p-main {
  padding-block-start: 5.69rem;
  display: flex;
  flex-direction: column;
  gap: 2.5rem;
  inline-size: 100%;
  max-inline-size: 85.5rem;
  margin: 0 auto;

  @media (min-width: 62.5rem) {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr;
    gap: 2.5rem;
    row-gap: 2rem;
    padding-block-start: 17.7rem;
  }

  &__quotation-image {
    position: absolute;
    inset-block-start: 24%;
    inset-inline-start: 37.5%;
    opacity: 0;

    @media (min-width: 62.5rem) {
      opacity: 0.7;
    }
  }
}

.p-footer {
  font-family: monospace;
  margin: 8rem auto;
  inline-size: fit-content;

  a {
    color: var(--color-purple-500);
  }

  &__attribution {
    border: 0.2rem solid var(--color-grey-400);
    margin: 1rem;
    padding: 1rem;
    text-align: center;
  }
}
</style>
