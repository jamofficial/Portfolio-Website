<script setup>
import { ref, computed } from "vue";

import LogoOpenMenu from "./icons/IconOpenMenu.vue";
import LogoCloseMenu from "./icons/IconCloseMenu.vue";
import LogoIcon from "./icons/IconLogo.vue";

defineProps({
  loc: {
    type: String,
    required: true,
  },
});
</script>

<template>
  <nav class="sticky top-0 w-full flex flex-wrap justify-between p-2">
    <div>
      <LogoIcon />
    </div>

    <ul id="menu" class="flex [&>li>a]:text-lg [&>li]:px-4">
      <li class="" id="home">
        <a href="#"> Home </a>
      </li>
      <li class="" id="about_me">
        <a href="#/about"> About Me </a>
      </li>
      <li class="" id="projects">
        <a href="#/projects"> Projects </a>
      </li>
      <li class="" id="contacts">
        <a href="#/contacts"> Contacts </a>
      </li>

      <div
        id="close-menu"
        onclick="document.getElementById('menu').style.right = '-100%'"
      >
        <LogoCloseMenu />
      </div>
    </ul>

    <div
      id="open-menu"
      onclick="document.getElementById('menu').style.right = '0'"
    >
      <LogoOpenMenu />
    </div>
  </nav>
</template>

<style scoped>
nav {
  background-color: var(--color-secondary);
}

#open-menu,
#close-menu {
  display: none;
  cursor: pointer;
}

#close-menu {
  position: absolute;
}

#close-menu {
  top: 0;
  right: 5px;
}

#menu {
  color: var(--text-body-secondary);
}

@media (max-width: 767px) {
  #close-menu,
  #open-menu {
    display: block;
  }

  #menu {
    position: fixed;
    z-index: 100;

    flex-direction: column;
    align-items: center;
    justify-content: center;

    width: 100%;
    height: 100vh;
    right: -100%;

    background-color: var(--color-secondary);

    transition: all 0.3s;
  }

  #menu li {
    margin-top: 40px;
  }

  #menu li a {
    font-size: var(--text-h3);
    font-family: var(--font-display);
  }
}
</style>
