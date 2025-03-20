<template>
  <div class="sidebar-card">
    <div
      class="icon-container"
      :style="{ backgroundColor: iconBackgroundColor }"
    >
      <i :class="icon" :style="{ color: iconColor }"></i>
    </div>
    <div class="course-details">
      <div class="course-title">{{ courseTitle }}</div>
      <div class="course-start-date">{{ startDate }}</div>
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
    iconColor: {
      type: String,
      required: true,
    },
    iconBackgroundColor: {
      type: String,
      required: true,
    },
    courseTitle: {
      type: String,
      required: true,
    },
    startDate: {
      type: String,
      required: true,
    },
  },
};
</script>

<style scoped>
.sidebar-card {
  display: flex;
  align-items: center;
  gap: 10px;
  padding: 10px;
  border-radius: 8px;
  color: #fff;
}

.icon-container {
  width: 40px;
  height: 40px;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 4px;
}

.icon-container i {
  font-size: 20px;
}

.course-details {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.course-title {
  font-size: 1rem;
  font-weight: 600;
}

.course-start-date {
  font-size: 0.9rem;
  color: #c1bfd6;
  margin-top: 5px;
}
</style>
