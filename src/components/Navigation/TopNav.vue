<template>
  <nav class="top-nav">
    <div class="container">
      <div class="logo">CodeCamp</div>
      <div class="menu-icon">
        <i class="fas fa-bars"></i>
      </div>

      <div class="right-icons">
        <div class="icon-container">
          <i class="far fa-chart-bar"></i>
        </div>
        <div class="icon-container">
          <i class="far fa-calendar"></i>
        </div>

        <div class="icon-container" title="Messages - Open inbox">
          <i class="far fa-envelope message-icon">
            <span class="message-dot"></span>
          </i>
        </div>
        <div class="icon-container notification">
          <i class="far fa-bell notification-icon">
            <span class="notification-dot"></span>
          </i>
        </div>

        <div class="profile">
          <img
            src="https://randomuser.me/api/portraits/women/28.jpg"
            alt="User"
          />
          <span class="online-indicator"></span>
        </div>
      </div>
    </div>
  </nav>
</template>

<style scoped>
.top-nav {
  background-color: #2e3348;
  color: #c1bfd6;
  height: 60px;
  width: 100%;
  display: flex;
  justify-content: center;
  border-bottom: 1px solid rgba(193, 191, 214, 0.5);
}

.container {
  width: 100%;
  max-width: 1400px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px;
}

.logo {
  font-family: "Unica One", sans-serif;
  font-size: 1.6rem;
}

.right-icons {
  display: flex;
  align-items: center;
}

.icon-container,
.menu-icon {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 36px;
  height: 36px;
  border-radius: 8px;
  transition: background-color 0.3s ease;
  cursor: pointer;
  position: relative;
}

.icon-container:hover,
.menu-icon:hover {
  background-color: rgba(193, 191, 214, 0.2);
}

.right-icons i,
.menu-icon i {
  font-size: 1.2rem;
  color: #c1bfd6;
  transition: color 0.3s ease;
}

.notification-icon {
  position: relative;
}

.notification-dot {
  width: 8px;
  height: 8px;
  background: #ff4c51;
  border-radius: 50%;
  position: absolute;
  top: -2px;
  right: -2px;
  border: 2px solid #2e3348;
}

.message-icon {
  position: relative;
}

.message-dot {
  width: 10px;
  height: 10px;
  background: skyblue;
  border-radius: 50%;
  position: absolute;
  bottom: -2px;
  right: -4px;
  border: 2px solid #2e3348;
}

.profile {
  position: relative;
  width: 36px;
  height: 36px;
  cursor: pointer;
  margin-left: 5px;
}

.profile img {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  object-fit: cover;
}

.online-indicator {
  width: 11px;
  height: 11px;
  background: #28c76f;
  border-radius: 50%;
  position: absolute;
  bottom: 0px;
  right: 0px;
  border: 2px solid #2e3348;
}

.menu-icon {
  display: none;
}

@media (max-width: 400px) {
  .logo {
    display: none;
  }

  .menu-icon {
    display: flex;
  }
}
</style>
