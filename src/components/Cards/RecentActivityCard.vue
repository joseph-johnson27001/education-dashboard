<template>
  <div class="recent-activity-card">
    <div class="activity-body">
      <div class="activity-title">{{ activity.title }}</div>
    </div>
    <div class="activity-header">
      <i class="fas fa-check-circle"></i>
      <!-- Icon indicating completed activity -->
      <span class="activity-time">{{ activity.time }}</span>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    activity: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
.recent-activity-card {
  background-color: #2e3348;
  border-radius: 8px;
  padding: 15px;
  color: #fff;
}

.activity-header {
  display: flex;
  align-items: center;
  gap: 5px;
  font-size: 14px;
}

.activity-header i {
  color: #28c76f;
  font-size: 15px;
}

.activity-time {
  color: #c1bfd6;
  font-size: 13px;
}

.activity-body {
  margin-bottom: 5px;
}

.activity-title {
  font-size: 16px;
  font-weight: 600;
  color: #fff;
}
</style>
