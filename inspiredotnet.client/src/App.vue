<template>
  <header>
  </header>
  <main>
    <router-view />
  </main>
    <footer>
      <div class="text-center p-2 footer-text">
        Made by garrett-adamss 
        <a class="footer-source" href="https://github.com/garrett-adamss/buglogger">
          &lt;source code/&gt;
        </a>
      </div>
    </footer>
</template>

<script>
import { computed } from 'vue'
import { AppState } from './AppState'
import Navbar from './components/Navbar.vue'

export default {
  setup() {
    return {
      appState: computed(() => AppState)
    }
  },
  components: { Navbar }
}
</script>
<style lang="scss">
@import "./assets/scss/main.scss";

:root{
  --main-height: calc(100vh - 32px - 64px);
}
a {
  color: black;
  text-decoration: none;
}

a:hover {
  color: black;
}
.footer-text{
  position: relative;
  bottom: 8px;
  font-size: 16px;
}

footer a {
    transition: transform 250ms;
}

footer a:hover {
  background-color: #555;
  color: white;
  transform: translateY(-10px);
}

footer {
  display: grid;
  place-content: center;
  height: 32px;
}
</style>
