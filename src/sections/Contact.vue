<script setup lang="ts">
import Button from '../components/Button.vue'
</script>

<template>
  <section id="contact">
    <h2 class="contact-title">Contact</h2>
    <div>
      <form
        action="POST"
        @submit="
          (e) => {
            e.preventDefault()
          }
        "
        class="contact-form"
      >
        <div class="select">
          <div class="select-option">
            <input type="radio" id="sayhi" name="option" value="sayhi" checked />
            <label for="sayhi">Say Hi!</label>
            <div class="select-bg"></div>
          </div>

          <div class="select-option">
            <input type="radio" id="idea" name="option" value="idea" />
            <label for="idea">Idea</label>
            <div class="select-bg"></div>
          </div>

          <div class="select-option">
            <input type="radio" id="hire" name="option" value="hire" />
            <label for="hire">Hire</label>
            <div class="select-bg"></div>
          </div>
        </div>
        <input type="email" name="" id="" placeholder="Enter email address" />
        <textarea name="" id="" placeholder="Hello World..."></textarea>
        <Button type="submit">Send</Button>
      </form>
    </div>
  </section>
</template>

<style scoped>
#contact {
  display: flex;
  flex-direction: column;
  align-items: center;
  box-sizing: border-box;
}

.contact-title {
  font-size: var(--font-section-title-size);
  font-weight: var(--font-section-title-weight);
  margin: 0;
  margin-bottom: 12px;
}

.contact-form {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 12px;
  font-family: var(--font-main);
  width: 372px;
  max-width: 372px;
}

.select {
  display: flex;
  gap: 12px;
  background: var(--grad-bg-10);
  width: fit-content;
  padding: 8px;
  border: 1px solid #ffffff;
  border-radius: 16px;
}

.select-option input[type='radio'] {
  display: none !important;
}

.select-option label {
  display: block;
  padding: 12px 24px;
  cursor: pointer;
  text-wrap: nowrap;
}

.select-option {
  --animation-speed: 0.2s;
  --animation-ease: ease-out;

  position: relative;
  width: min-content;
  color: var(--color-text);
  border: 1px solid #ffffff33;
  border-radius: 8px;
  font-family: var(--font-main);
  font-size: 16px;
  font-weight: 700;
  background: var(--grad-bg-10);
  text-shadow: 0px 0px 0px white;
  overflow: hidden;

  transition:
    border-color var(--animation-speed) var(--animation-ease),
    text-shadow var(--animation-speed) var(--animation-ease);
}

.select-option:hover {
  border-color: #ffffffb3;
  text-shadow: 0px 0px 6px white;
}

.select-bg {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;

  z-index: -1;

  background: var(--grad-bg-100);
  opacity: 0.1;
  transition: opacity var(--animation-speed) var(--animation-ease);
}

.select-option:hover .select-bg {
  opacity: 0.3;
}

.select-option:has(input:checked) {
  background: var(--grad-bg-30);
  background-color: var(--color-main);

  animation: pulse 0.5s ease-out forwards;
}

.contact-form input[type='email'],
.contact-form textarea {
  padding: 12px 24px;
  border: 1px solid #ffffff33;
  border-radius: 8px;
  background: #1d1d1d;
  color: var(--color-text);
  font-family: var(--font-main);
  font-size: 16px;
  width: 100%;
}

.contact-form input[type='email']::placeholder,
.contact-form textarea::placeholder {
  color: #ffffff99;
}

.contact-form textarea {
  min-width: 100%;
  max-width: 100%;
  min-height: 140px;
}

.contact-form button[type='submit'] {
  width: fit-content;
}

@keyframes pulse {
  from {
    outline: 0px solid #ffffff;
  }

  to {
    outline: 6px solid #ffffff00;
  }
}
</style>
