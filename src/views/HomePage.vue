<template>
  <div class="home-page">
    <div class="heading-area">
      <div>
        <div class="welcome-heading">
          Welcome back, Joanne!
          <i class="far fa-solid fa-star"></i>
        </div>
        <div class="welcome-container">
          <div class="welcome-back-message">
            Keep pushing forward, your next milestone is just around the corner.
            Let's get studying!
          </div>
          <div class="start-next-class-button-container">
            <button class="next-class-button">Begin Next Class</button>
          </div>
        </div>
        <div class="kpi-area">
          <KpiCard
            v-for="(kpi, index) in kpiData"
            :key="index"
            :icon="kpi.icon"
            :label="kpi.label"
            :value="kpi.value"
            :iconColor="kpi.iconColor"
          />
        </div>
      </div>

      <div class="donut-chart-container">
        <div class="stats-section">
          <div class="weekly-stats">
            <div class="stats-heading">This Week:</div>
            <div class="stats-time">{{ weeklyStats.time }}</div>
            <div class="stats-change">{{ weeklyStats.change }}</div>
          </div>

          <div class="monthly-stats">
            <div class="stats-heading">This Month:</div>
            <div class="stats-time">{{ monthlyStats.time }}</div>
            <div class="stats-change">{{ monthlyStats.change }}</div>
          </div>
        </div>

        <div class="donut-chart-section">
          <DonutChart />
        </div>
      </div>
    </div>

    <div class="main-content">
      <div class="chart-area">
        <h3>Course Progression</h3>
        <ProgressChart />
      </div>

      <div class="sidebar-area">
        <div class="upcoming-courses">
          <h3>Upcoming Courses</h3>
          <SideBarCard
            v-for="(course, index) in upcomingCourses"
            :key="index"
            :icon="course.icon"
            :iconColor="course.iconColor"
            :iconBackgroundColor="course.iconBackgroundColor"
            :courseTitle="course.title"
            :startDate="course.startDate"
          />
        </div>
      </div>
    </div>

    <div class="bottom-content">
      <div class="bottom-left-area">
        <div class="instructors-area">
          <h3>Popular Instructors</h3>
          <InstructorsCard
            v-for="(instructor, index) in instructors"
            :key="index"
            :profileImage="instructor.profileImage"
            :instructorName="instructor.name"
            :area="instructor.area"
          />
        </div>

        <div class="assignments-area">
          <h3>Upcoming Assignments</h3>
          <UpcomingAssignmentsCard
            v-for="(assignment, index) in upcomingAssignments"
            :key="index"
            :assignmentTitle="assignment.title"
            :dueDate="assignment.dueDate"
            :iconColor="assignment.iconColor"
            :icon="assignment.icon"
            :iconBackgroundColor="assignment.iconBackgroundColor"
          />
        </div>
      </div>

      <div class="recent-activity-area">
        <h3>Recent Activity</h3>
        <RecentActivityCard
          v-for="(activity, index) in recentActivities"
          :key="index"
          :activity="activity"
        />
      </div>
    </div>
  </div>
</template>

<script>
import KpiCard from "@/components/KPIs/KpiCard.vue";
import ProgressChart from "@/components/Charts/ProgressChart.vue";
import DonutChart from "@/components/Charts/DonutChart.vue";
import SideBarCard from "@/components/Sidebar/SideBarCard.vue";
import InstructorsCard from "@/components/Cards/InstructorsCard.vue";
import RecentActivityCard from "@/components/Cards/RecentActivityCard.vue";
import UpcomingAssignmentsCard from "@/components/Cards/UpcomingAssignmentsCard.vue";

export default {
  components: {
    KpiCard,
    ProgressChart,
    DonutChart,
    SideBarCard,
    InstructorsCard,
    RecentActivityCard,
    UpcomingAssignmentsCard,
  },
  data() {
    return {
      kpiData: [
        {
          icon: "fa fa-laptop",
          label: "Courses Completed",
          value: "12",
          iconColor: "#3498db",
        },
        {
          icon: "far fa-clock",
          label: "Time Studied",
          value: "120 hrs",
          iconColor: "#00bcd4",
        },
        {
          icon: "far fa-chart-bar",
          label: "Average Course Score",
          value: "85%",
          iconColor: "#ff9f43",
        },
        {
          icon: "far fa-calendar-check",
          label: "Upcoming Deadline",
          value: "March 25th",
          iconColor: "#28c76f",
        },
        {
          icon: "fa fa-medal",
          label: "Total Achievements",
          value: "5",
          iconColor: "#9b59b6",
        },
        {
          icon: "far fa-lightbulb",
          label: "Completed Challenges",
          value: "8",
          iconColor: "#ffde21",
        },
      ],
      upcomingCourses: [
        {
          icon: "fas fa-laptop-code",
          iconColor: "rgba(255, 159, 67, 1)",
          iconBackgroundColor: "rgba(255, 159, 67, 0.2)",
          title: "Web Development Basics",
          startDate: "March 25, 2025",
        },
        {
          icon: "fas fa-database",
          iconColor: "rgba(46, 204, 113, 1)",
          iconBackgroundColor: "rgba(46, 204, 113, 0.2)",
          title: "Data Science Essentials",
          startDate: "April 1, 2025",
        },
        {
          icon: "fas fa-cloud",
          iconColor: "rgba(52, 152, 219, 1)",
          iconBackgroundColor: "rgba(52, 152, 219, 0.2)",
          title: "Cloud Computing Introduction",
          startDate: "April 10, 2025",
        },
        {
          icon: "fas fa-paint-brush",
          iconColor: "rgba(231, 76, 60, 1)",
          iconBackgroundColor: "rgba(231, 76, 60, 0.2)",
          title: "Creative Design Principles",
          startDate: "April 15, 2025",
        },
        {
          icon: "fas fa-chart-line",
          iconColor: "rgba(241, 196, 15, 1)",
          iconBackgroundColor: "rgba(241, 196, 15, 0.2)",
          title: "Business Analytics 101",
          startDate: "April 20, 2025",
        },
      ],
      upcomingAssignments: [
        {
          title: "JavaScript Assignment",
          dueDate: "March 27, 2025",
          icon: "fas fa-code",
          iconColor: "rgba(52, 152, 219, 1)",
          iconBackgroundColor: "rgba(52, 152, 219, 0.2)",
        },
        {
          title: "Database Project",
          dueDate: "April 5, 2025",
          icon: "fas fa-database",
          iconColor: "rgba(46, 204, 113, 1)",
          iconBackgroundColor: "rgba(46, 204, 113, 0.2)",
        },
        {
          title: "Cloud Computing Lab",
          dueDate: "April 12, 2025",
          icon: "fas fa-cloud",
          iconColor: "rgba(241, 196, 15, 1)",
          iconBackgroundColor: "rgba(241, 196, 15, 0.2)",
        },
        {
          title: "React Native Mobile App",
          dueDate: "April 18, 2025",
          icon: "fas fa-mobile-alt",
          iconColor: "rgba(231, 76, 60, 1)",
          iconBackgroundColor: "rgba(231, 76, 60, 0.2)",
        },
      ],
      weeklyStats: {
        time: "18hrs 44mins",
        change: "+6.2%",
      },
      monthlyStats: {
        time: "82hrs 15mins",
        change: "+12.8%",
      },
      instructors: [
        {
          profileImage: "https://randomuser.me/api/portraits/men/45.jpg",
          name: "John Doe",
          area: "Frontend Development",
        },
        {
          profileImage: "https://randomuser.me/api/portraits/women/12.jpg",
          name: "Jane Smith",
          area: "Data Science",
        },
        {
          profileImage: "https://randomuser.me/api/portraits/men/30.jpg",
          name: "Mark Johnson",
          area: "Backend Development",
        },
        {
          profileImage: "https://randomuser.me/api/portraits/women/30.jpg",
          name: "Betty Adams",
          area: "Database Management",
        },
      ],
      recentActivities: [
        {
          title: "Completed 'Web Development Basics' course",
          time: "2 hours ago",
        },
        {
          title: "Started 'Cloud Computing Introduction' course",
          time: "1 day ago",
        },
        {
          title: "Reviewed 'Data Science Essentials' materials",
          time: "3 days ago",
        },
        {
          title: "Completed 'Cloud Computing Lab' assignment",
          time: "5 days ago",
        },
      ],
    };
  },
};
</script>

<style scoped>
.home-page {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.fa-star {
  color: gold;
  font-size: 1.4rem;
}

.kpi-area {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}

.heading-area {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 20px;
}

.donut-chart-container {
  display: flex;
  gap: 20px;
  align-items: center;
}

.stats-section {
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  gap: 10px;
  height: 100%;
}

.weekly-stats,
.monthly-stats {
  display: flex;
  flex-direction: column;
  border-radius: 8px;
}

.stats-heading {
  font-size: 1rem;
  font-family: "Inter";
  color: #fff;
  margin-bottom: 8px;
}

.stats-time {
  font-size: 16px;
  color: #c1bfd6;
  margin-bottom: 8px;
}

.stats-change {
  font-size: 14px;
  font-weight: 600;
  color: #28c76f;
  background-color: rgba(40, 199, 111, 0.2);
  padding: 5px 10px;
  border-radius: 6px;
  width: 70px;
}

.donut-chart-section {
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 8px;
}

.main-content {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 20px;
  box-sizing: border-box;
}

.chart-area {
  background-color: #2e3348;
  border-radius: 8px;
  color: #c1bfd6;
  display: flex;
  padding: 20px;
  flex-direction: column;
  overflow-x: scroll;
  scrollbar-width: none;
  -ms-overflow-style: none;
}

.chart-area ::-webkit-scrollbar {
  display: none; /* Chrome, Safari, and Opera */
}

.welcome-heading {
  padding-top: 10px;
  font-size: 20px;
  color: #fff;
}

.welcome-container {
  display: flex;
  align-items: flex-end;
  justify-content: space-between;
}

.welcome-back-message {
  font-size: 14px;
  color: #c1bfd6;
  margin-bottom: 20px;
  font-weight: 600;
}

.start-next-class-button-container {
  margin-left: auto;
  display: flex;
  align-items: center;
}

.next-class-button {
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
  transition: background-color 0.2s linear;
  margin-bottom: 10px;
}

.next-class-button:hover {
  background-color: #5f4bdb;
}

.sidebar-area {
  background-color: #2e3348;
  border-radius: 8px;
  color: #c1bfd6;
  display: flex;
  padding: 20px;
  flex-direction: column;
}

h3 {
  font-size: 1rem;
  font-family: "Inter";
  color: #fff;
  font-weight: 400;
  margin-bottom: 10px;
}

.bottom-content {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 20px;
}

.bottom-left-area {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
}

.instructors-area,
.assignments-area,
.recent-activity-area {
  background-color: #2e3348;
  padding: 20px;
  gap: 20px;
  box-sizing: border-box;
  border-radius: 8px;
}

@media (max-width: 1000px) {
  .heading-area,
  .main-content,
  .bottom-content,
  .bottom-left-area {
    grid-template-columns: 1fr;
  }

  .kpi-area {
    grid-template-columns: 1fr 1fr;
  }

  .donut-chart-container {
    justify-content: space-around;
  }

  .stats-section {
    flex-direction: row;
    align-items: center;
    text-align: center;
    justify-content: space-between;
  }
}

@media (max-width: 600px) {
  .kpi-area,
  .donut-chart-container {
    grid-template-columns: 1fr;
  }
  .donut-chart-container {
    flex-direction: column;
  }
  .welcome-container {
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  .start-next-class-button-container {
    margin: auto;
  }
}
</style>
