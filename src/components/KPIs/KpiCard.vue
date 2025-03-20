<template>
  <div class="kpi-card">
    <div class="icon-container">
      <i :class="icon" :style="{ color: iconColor }"></i>
    </div>
    <div class="info">
      <div class="label">{{ label }}</div>
      <div class="value">{{ value }}</div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    icon: {
      type: String,
      required: true,
    },
    label: {
      type: String,
      required: true,
    },
    value: {
      type: String,
      required: true,
    },
    iconColor: {
      type: String,
      default: "#ff9f43",
    },
  },
};
</script>

<style scoped>
.kpi-card {
  background-color: #2e3348;
  color: #fff;
  padding: 20px 15px;
  height: 80px;
  border-radius: 8px;
  display: flex;
  align-items: center;
}

.icon-container {
  display: flex;
  margin-right: 10px;
  width: 30px;
  height: 30px;
  align-items: center;
}

.icon-container i {
  font-size: 1.6rem;
  transition: color 0.3s ease;
}

.info {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.label {
  font-size: 0.9rem;
  color: #c1bfd6;
  margin-bottom: 5px;
}

.value {
  text-align: right;
  font-size: 0.9rem;
  font-weight: bold;
}
</style>
