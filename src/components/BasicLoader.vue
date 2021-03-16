<template>
  <div class="loader-dots-container">
    <div
      v-for="n in 3"
      class="loader-dot"
      :class="{ 'active-dot': activeDot === n }"
      :key="n"
    ></div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeDot: 1,
    };
  },
  mounted() {
    setInterval(() => {
      this.activeDot = this.activeDot === 3 ? 1 : this.activeDot + 1;
    }, 500);
  },
};
</script>

<style lang="scss" scoped>
.loader-dots-container {
  display: flex;
  justify-content: center;
  align-items: center;
}

.loader-dot {
  height: 25px;
  width: 25px;
  border-radius: 50%;
  background-color: #555956;
  margin: 0 0.3rem;
}

.active-dot {
  background-color: #adb3ae;
}
</style>
