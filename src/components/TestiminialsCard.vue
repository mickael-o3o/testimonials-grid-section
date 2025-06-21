<script setup lang="ts">
interface Props {
  background: string
  textColorBlack?: boolean
  userPicture: string
  userName: string
  message: string
  messageDetails: string
  colSpan?: string
  rowSpan?: string
}

const { background, textColorBlack, userPicture, userName, colSpan, rowSpan } = defineProps<Props>()
</script>

<template>
  <article
    class="c-testimoials-card"
    :style="{ background: background, gridColumn: colSpan, gridRow: rowSpan }"
  >
    <header
      class="c-testimoials-card__header"
      :class="{ 'c-testimoials-card__header--black': textColorBlack }"
    >
      <img
        :src="userPicture"
        alt="user pitcure"
        class="c-testimoials-card__user-image"
        :class="{ 'c-testimoials-card__user-image--black': textColorBlack }"
        width="56px"
        height="56px"
      />
      <div class="c-testimoials-card__user-identity">
        <h3 class="c-testimoials-card__user-name">{{ userName }}</h3>
        <p
          class="c-testimoials-card__user-status"
          :class="{ 'c-testimoials-card__user-status--black': textColorBlack }"
        >
          Verified Graduate
        </p>
      </div>
    </header>
    <div class="c-testimoials-card__body">
      <p
        class="c-testimoials-card__message"
        :class="{ 'c-testimoials-card__message--black': textColorBlack }"
      >
        {{ message }}
      </p>
      <p
        class="c-testimoials-card__message-details"
        :class="{ 'c-testimoials-card__message-details--black': textColorBlack }"
      >
        {{ messageDetails }}
      </p>
    </div>
  </article>
</template>

<style scoped lang="scss">
.c-testimoials-card {
  background: var(--color-purple-500);
  color: var(--color-white);
  padding: 2.4rem;
  padding-block-start: 2.3rem;
  border-radius: 0.4rem;
  box-shadow: 2rem 5rem 2rem var(--color-grey-200);
  max-inline-size: 40rem;
  margin: 0 auto;

  @media (min-width: 62.5rem) {
    max-inline-size: 100%;
  }

  &__header {
    margin-block-end: 1.2rem;
    display: flex;
    align-items: center;
    gap: 1.1rem;

    &--black {
      color: var(--color-grey-500);
    }
  }

  &__user-image {
    border: 0.2rem solid var(--color-purple-300);
    border-radius: 100%;
    inline-size: 2.4rem;
    block-size: auto;

    &--black {
      border: 0.3rem solid var(--color-purple-50);
    }
  }

  &__user-identity {
    display: flex;
    flex-direction: column;
    gap: 0.15rem;
  }

  &__user-name {
    font-size: 1rem;
  }

  &__user-status {
    font-size: 0.85rem;
    color: var(--color-grey-200);

    &--black {
      color: var(--color-grey-400);
    }
  }

  &__body {
    margin-inline-start: 0.2rem;
  }

  &__message {
    font-family: var(--font-family-bold);
    font-size: 1.5rem;
    margin-block-end: 1.2rem;

    &--black {
      color: var(--color-grey-500);
    }
  }

  &__message-details {
    line-height: 1.4;
    color: var(--color-grey-100);

    &--black {
      color: var(--color-grey-400);
    }
  }
}
</style>
