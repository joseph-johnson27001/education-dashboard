<template>
  <div class="instructor-card">
    <div class="profile-container">
      <img class="profile-image" :src="profileImage" alt="Instructor Profile" />
    </div>
    <div class="instructor-details">
      <div class="instructor-name">{{ instructorName }}</div>
      <div class="instructor-area">{{ area }}</div>
    </div>
    <button class="view-button">View</button>
  </div>
</template>

<script>
export default {
  props: {
    profileImage: {
      type: String,
      required: true,
    },
    instructorName: {
      type: String,
      required: true,
    },
    area: {
      type: String,
      required: true,
    },
  },
  methods: {},
};
</script>

<style scoped>
.instructor-card {
  display: flex;
  align-items: center;
  padding: 10px;
  border-radius: 8px;
  color: #fff;
  width: 100%;
}

.profile-container {
  width: 40px;
  height: 40px;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 50%;
  overflow: hidden;
}

.profile-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.instructor-details {
  display: flex;
  flex-direction: column;
  margin-left: 10px;
}

.instructor-name {
  font-size: 1rem;
  font-weight: 600;
  color: #fff;
}

.instructor-area {
  font-size: 0.9rem;
  color: #c1bfd6;
}

.view-button {
  margin-left: auto;
  font-family: "Inter";
  background: linear-gradient(
    270deg,
    rgba(115, 103, 240, 0.7),
    rgb(115, 103, 240)
  );
  color: #fff;
  border: none;
  padding: 8px 16px;
  font-size: 0.9rem;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.2s ease;
}

.view-button:hover {
  background-color: #5f4bdb;
}

@media (max-width: 400px) {
  .instructor-card {
    flex-wrap: wrap;
  }
  .view-button {
    margin-right: auto;
    margin-left: 0;
    margin-top: 10px;
    width: 100%;
  }
}
</style>
