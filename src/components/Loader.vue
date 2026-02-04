<template>
  <div
    class="loader"
    role="status"
    aria-label="Загрузка"
  >
    <div
      v-for="(_, index) in items"
      :key="index"
      class="loader-item"
      :class="`loader-item--${index + 1}`"
    />
  </div>
</template>

<script>
export default {
  name: 'Loader',
  data() {
    return {
      itemCount: 3,
    }
  },
  computed: {
    items() {
      return Array.from({ length: this.itemCount }, (_, i) => i)
    },
  },
}
</script>

<style scoped>
.loader {
  position: relative;
  width: 100px;
  height: 100px;
  border-radius: 50%;
  perspective: 800px;
}

.loader-item {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border-radius: 50%;
}

.loader-item--1 {
  border-bottom: 6px solid rgb(245, 35, 165);
  transform: rotateX(35deg) rotateY(-45deg);
  animation: rotate-one 1s linear infinite;
}

.loader-item--2 {
  border-bottom: 6px solid rgb(61, 245, 14);
  transform: rotateX(50deg) rotateY(10deg);
  animation: rotate-two 1s linear infinite;
}

.loader-item--3 {
  border-bottom: 6px solid rgb(240, 18, 55);
  transform: rotateX(35deg) rotateY(55deg);
  animation: rotate-three 1s linear infinite;
}

@keyframes rotate-one {
  to {
    transform: rotateX(35deg) rotateY(-45deg) rotateZ(360deg);
  }
}

@keyframes rotate-two {
  to {
    transform: rotateX(50deg) rotateY(10deg) rotateZ(360deg);
  }
}

@keyframes rotate-three {
  to {
    transform: rotateX(35deg) rotateY(55deg) rotateZ(360deg);
  }
}
</style>
