<template>
  <div>
    <the-header></the-header>
    <!-- <badge-list></badge-list>
    <user-info
      :full-name="activeUser.name"
      :info-text="activeUser.description"
      :role="activeUser.role"
    ></user-info>
    <course-goal #default="slotProps">
      <h2>{{ slotProps.goal }}</h2>
      <p>{{ slotProps.anotherProp }}</p>
    </course-goal> -->
    <button @click="setSelectedComponent('active-goal')">Active goals</button>
    <button @click="setSelectedComponent('manage-goal')">Manage goals</button>
    <keep-alive>
      <component :is="selectedComponent"></component>
    </keep-alive>
  </div>
</template>

<script>
// import BadgeList from './components/BadgeList';
// import UserInfo from './components/UserInfo';
// import CourseGoal from './components/CourseGoal';
import TheHeader from './components/layouts/TheHeader';
import ManageGoal from './components/ManageGoal';
import ActiveGoal from './components/ActiveGoal';

export default {
  components: {
    TheHeader,
    ManageGoal,
    ActiveGoal,
    // BadgeList,
    // UserInfo,
    // CourseGoal,
  },
  data() {
    return {
      activeUser: {
        name: 'Maximilian Schwarzmüller',
        description: 'Site owner and admin',
        role: 'admin',
      },
      selectedComponent: 'active-goal',
    };
  },
  methods: {
    setSelectedComponent(cmp) {
      this.selectedComponent = cmp;
    }
  },
};
</script>

<style>
html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
</style>