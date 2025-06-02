<script setup lang="ts">
import { ref } from 'vue'
import Button from '../components/Button.vue'

const sentMessage = ref(false)
</script>

<template>
  <section id="contact">
    <h2 class="contact-title">Contact</h2>
    <div v-if="!sentMessage">
      <form
        @submit="
          (e) => {
            sendMessage(e).finally(() => {
              sentMessage = true
            })
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
        <input type="email" name="email" id="email" placeholder="Enter email address" />
        <textarea name="message" id="message" placeholder="Hello World..."></textarea>
        <Button id="submit-btn" type="submit">Send</Button>
        <input type="hidden" name="_captcha" value="false" />
        <input type="text" name="_honey" style="display: none" />
      </form>
    </div>
    <p v-if="sentMessage">
      Thanks for reaching out! I'll respond to your message as soon as possible
    </p>
    <div class="contact-other">
      <a href="mailto:jcbkdev@gmail.com">
        <svg
          width="21"
          height="17"
          viewBox="0 0 21 17"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M1.5 3.5C1.5 2.96957 1.71071 2.46086 2.08579 2.08579C2.46086 1.71071 2.96957 1.5 3.5 1.5H17.5C18.0304 1.5 18.5391 1.71071 18.9142 2.08579C19.2893 2.46086 19.5 2.96957 19.5 3.5M1.5 3.5V13.5C1.5 14.0304 1.71071 14.5391 2.08579 14.9142C2.46086 15.2893 2.96957 15.5 3.5 15.5H17.5C18.0304 15.5 18.5391 15.2893 18.9142 14.9142C19.2893 14.5391 19.5 14.0304 19.5 13.5V3.5M1.5 3.5L10.5 9.5L19.5 3.5"
            stroke="white"
            stroke-width="2"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
        </svg>

        <span>jcbkdev@gmail.com</span>
      </a>
      <a href="https://linkedin.com/in/jcbkdev/" target="_blank" rel="noopener noreferrer">
        <svg
          width="21"
          height="21"
          viewBox="0 0 21 21"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M6.5 9.5V14.5M6.5 6.5V6.51M10.5 14.5V9.5M14.5 14.5V11.5C14.5 10.9696 14.2893 10.4609 13.9142 10.0858C13.5391 9.71071 13.0304 9.5 12.5 9.5C11.9696 9.5 11.4609 9.71071 11.0858 10.0858C10.7107 10.4609 10.5 10.9696 10.5 11.5M1.5 5.5C1.5 4.43913 1.92143 3.42172 2.67157 2.67157C3.42172 1.92143 4.43913 1.5 5.5 1.5H15.5C16.5609 1.5 17.5783 1.92143 18.3284 2.67157C19.0786 3.42172 19.5 4.43913 19.5 5.5V15.5C19.5 16.5609 19.0786 17.5783 18.3284 18.3284C17.5783 19.0786 16.5609 19.5 15.5 19.5H5.5C4.43913 19.5 3.42172 19.0786 2.67157 18.3284C1.92143 17.5783 1.5 16.5609 1.5 15.5V5.5Z"
            stroke="white"
            stroke-width="2"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
        </svg>

        <span>Linkedin</span>
      </a>
      <a href="https://github.com/jcbkdev" target="_blank" rel="noopener noreferrer">
        <svg
          width="20"
          height="21"
          viewBox="0 0 20 21"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M7.52601 17.4913C3.20737 18.8974 3.20737 14.9805 1.5 14.4783M13.552 19.5V15.9848C13.552 14.9805 13.6524 14.5788 13.0498 13.9762C15.862 13.6749 18.5737 12.5701 18.5737 7.95015C18.5725 6.74994 18.1042 5.59731 17.2681 4.73628C17.6602 3.69375 17.6241 2.53842 17.1676 1.52241C17.1676 1.52241 16.0629 1.22111 13.6524 2.82805C11.6109 2.29634 9.46715 2.29634 7.42557 2.82805C5.01517 1.22111 3.9104 1.52241 3.9104 1.52241C3.45391 2.53842 3.41781 3.69375 3.80997 4.73628C2.97381 5.59731 2.50556 6.74994 2.50433 7.95015C2.50433 12.5701 5.21604 13.6749 8.02817 13.9762C7.42557 14.5788 7.42557 15.1814 7.52601 15.9848V19.5"
            stroke="white"
            stroke-width="2.00867"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
        </svg>
        <span>Github</span>
      </a>
    </div>
  </section>
</template>

<script lang="ts">
async function sendMessage(e: Event) {
  e.preventDefault()

  const form = e.target as HTMLFormElement
  if (!form) return

  const submitButton = document.getElementById('submit-btn') as HTMLButtonElement | null
  if (submitButton) submitButton.disabled = true

  const formData = new FormData(form)

  if (formData.get('_honey')) return

  try {
    const response = await fetch('https://formsubmit.co/ajax/jcbkdev@gmail.com', {
      method: 'POST',
      headers: {
        Accept: 'application/json',
      },
      body: formData,
    })

    const result = await response.json()

    if (!response.ok) {
      alert('Failed to send message: ' + result.message)
    } else {
      form.reset()
    }
  } catch (error) {
    alert('Error sending message. Please try again later.')
    console.error(error)
  }
}
</script>

<style scoped>
#contact {
  display: flex;
  flex-direction: column;
  align-items: center;
  box-sizing: border-box;
  gap: 24px;
}

.contact-title {
  font-size: var(--font-section-title-size);
  font-weight: var(--font-section-title-weight);
  margin: 0;
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

.contact-other {
  display: flex;
  flex-direction: column;
  gap: 4px;
}

.contact-other a {
  display: flex;
  align-items: center;
  gap: 12px;

  text-decoration: none;
  color: white;
  font-weight: 700;
  font-size: 18px;
  transition: 0.3s ease;

  background-color: none;
  padding: 4px 12px;
  border-radius: 32px;
}

.contact-other a path {
  transition: 0.3s ease;
}

.contact-other a:hover {
  background-color: #5e5e5e5d;
  color: var(--color-hover);
  box-shadow: 0 0 16px var(--color-hover);
}

.contact-other a:hover path {
  stroke: var(--color-hover);
}

@media screen and (max-width: 640px) {
  .contact-form {
    box-sizing: border-box;
    padding: 0 24px;
  }
  .contact-form input,
  .contact-form textarea {
    width: 100%;
    box-sizing: border-box;
  }
}
</style>
