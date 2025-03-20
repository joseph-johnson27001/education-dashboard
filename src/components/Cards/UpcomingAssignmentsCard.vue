<template>
  <div class="sidebar-card">
    <div
      class="icon-container"
      :style="{ backgroundColor: iconBackgroundColor }"
    >
      <i :class="icon" :style="{ color: iconColor }"></i>
    </div>
    <div class="assignment-details">
      <div class="assignment-title">{{ assignmentTitle }}</div>
      <div class="assignment-due-date">{{ dueDate }}</div>
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
    assignmentTitle: {
      type: String,
      required: true,
    },
    dueDate: {
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

.assignment-details {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.assignment-title {
  font-size: 1rem;
  font-weight: 600;
}

.assignment-due-date {
  color: #c1bfd6;
  font-size: 13px;
}
</style>
