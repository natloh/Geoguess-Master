<template>
  <div class="score-board">
    <div class="content-container">
      <div class="content-wrapper">
        <span class="sub-text">Map</span>
        <br />
        <span id="selected-map" class="main-text">{{ selectedMap }}</span>
      </div>
      <div class="content-wrapper">
        <span class="sub-text">Round</span>
        <br />
        <span id="round" class="main-text">{{ round }} / 5</span>
      </div>
      <div class="content-wrapper">
        <span class="sub-text">Score</span>
        <br />
        <span id="score" class="main-text">{{ score }}</span>
      </div>
      <div v-if="selectedMode === 'multiplayer'" class="content-wrapper">
        <span class="sub-text">Time</span>
        <br />
        <span id="time" class="main-text">{{ countdown }}</span>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  props: {
    selectedMap: {
      type: String,
      required: true,
    },
    selectedMode: {
      type: String,
      required: true,
    },
    round: {
      type: Number,
      required: true,
    },
    score: {
      type: Number,
      required: true,
    },
    countdown: {
      type: String,
    },
  },
});
</script>

<style scoped>
.score-board {
  position: absolute;
  top: 12px;
  left: 12px;
  width: 240px;
  height: 64px;
  padding: 0 16px;
  border-radius: 5px;
  background-color: #0000ae;
  z-index: 1;
  display: flex;
  align-items: center;
  justify-content: center;
}

.content-container {
  display: flex;
  flex-direction: row;
}

.content-wrapper {
  margin-right: 16px;
}

.main-text {
  color: #ffffff;
  font-family: "Roboto medium";
  font-size: 16px;
}

.sub-text {
  color: #ffffff;
  font-family: "Roboto medium";
  font-size: 12px;
}
</style>
