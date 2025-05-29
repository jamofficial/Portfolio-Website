<script setup>
import { ref, watchEffect } from "vue";

import Button from "./components/Button.vue";

const proxyUrl = "https://api.allorigins.win/raw?url=";
const targetUrl =
  "https://wakatime.com/api/v1/users/@jamofficial/stats/last_7_days";

const stats = ref(null);

watchEffect(async () => {
  const url = `${proxyUrl}${targetUrl}`;
  stats.value = await (await fetch(url)).json();
});
</script>

<template>
  <main
    class="w-screen flex flex-col-reverse md:flex-row md:justify-evenly m-auto"
  >
    <hgroup
      class="w-sm px-1 m-auto md:mb-auto md:ml-[5rem] md:w-1/2 content-center"
    >
      <!-- Header Texts -->
      <div>
        <p class="ml-[24px] md:m-0 text-base md:text-lg font-body">Hi, I am</p>
        <h1
          class="text-h1 md:text-h1-lg text-center md:text-start font-display"
        >
          Jhaime Cando
        </h1>
        <p
          class="text-sm md:text-base text-center md:text-start font-body text-(--color-accent)"
        >
          Graduating Computer Science Student
        </p>
        <p class="w-xs text-base md:text-lg font-body m-auto md:m-0 md:w-lg">
          An aspiring software engineer. This portfolio showcases my journey,
          projects, and the technologies I’m excited to work with.
        </p>
      </div>

      <!-- Buttons -->
      <div
        class="flex flex-col md:flex-row mt-[24px] justify-around md:justify-start [&>a]:mb-[24px] md:[&>a]:mr-[24px]"
      >
        <Button
          name="Download Resume"
          btn_type="primary"
          url="/Resume.pdf"
          :download="true"
          filename="Resume.pdf"
        />
        <Button
          name="WakaTime"
          btn_type="ghost"
          url="https://wakatime.com/@jamofficial"
        />
        <Button
          name="GitHub"
          btn_type="ghost"
          url="https://github.com/jhaimecando27"
        />
      </div>
    </hgroup>

    <picture class="my-[24px] md:w-1/2 flex justify-center">
      <img
        class="w-2/4 md:w-100"
        src="./assets/img/hero_image.png"
        alt="Portrait of Jhaime Cando animated by AI"
      />
    </picture>
  </main>
</template>

<style scoped></style>
