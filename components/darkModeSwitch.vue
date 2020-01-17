<template>
  <div>
    <div class="flex w2 h1 br4 bg-inverted-50" @click="changeMode()">
      <div v-if="isWhiteMode" class="dib w1 h1 inverted-100" style="padding: 0 0.15rem">
        <svg
          viewBox="0 0 24 24"
          stroke="currentColor"
          stroke-width="2"
          fill="none"
          stroke-linecap="round"
          stroke-linejoin="round"
        >
          <circle cx="12" cy="12" r="5" />
          <line x1="12" y1="1" x2="12" y2="3" />
          <line x1="12" y1="21" x2="12" y2="23" />
          <line x1="4.22" y1="4.22" x2="5.64" y2="5.64" />
          <line x1="18.36" y1="18.36" x2="19.78" y2="19.78" />
          <line x1="1" y1="12" x2="3" y2="12" />
          <line x1="21" y1="12" x2="23" y2="12" />
          <line x1="4.22" y1="19.78" x2="5.64" y2="18.36" />
          <line x1="18.36" y1="5.64" x2="19.78" y2="4.22" />
        </svg>
      </div>

      <button
        type="button"
        class="overflow-hidden button-reset dib w1 h1 br4 bg-inverted-100"
        aria-label="Dark mode"
        aria-pressed="false"
      />

      <div v-if="isDarkMode" class="dib w1 h1 inverted-100" style="padding: 0 0.1rem">
        <svg
          viewBox="0 0 24 24"
          stroke="currentColor"
          stroke-width="2"
          fill="none"
          stroke-linecap="round"
          stroke-linejoin="round"
        >
          <path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z" />
        </svg>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      mode: "dark"
    };
  },
  computed: {
    isDarkMode() {
      return this.mode === "dark";
    },
    isWhiteMode() {
      return this.mode === "white";
    },
    isWTFMode() {
      return this.mode === "wtf";
    }
  },
  methods: {
    changeMode(newMode = "auto") {
      if (newMode === "auto") {
        this.mode = !this.isDarkMode ? "dark" : "white";
      } else {
        this.mode = newMode;
      }

      if (this.mode === "white") {
        window.document.body.classList.add("light-mode");
      } else {
        window.document.body.classList.remove("light-mode");
      }
    }
  }
};
</script>