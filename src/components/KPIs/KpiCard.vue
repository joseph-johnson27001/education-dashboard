<template>
  <div class="kpi-card">
    <div class="icon-container">
      <i :class="icon"></i>
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
}

.icon-container i {
  font-size: 1.4rem;
  color: #c1bfd6;
  transition: color 0.3s ease;
}

.info {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.label {
  font-size: 0.8rem;
  color: #c1bfd6;
}

.value {
  text-align: right;
  font-size: 0.9rem;
  font-weight: bold;
}
</style>
