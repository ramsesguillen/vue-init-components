<template>
  <section>
    <base-card>
      <template #header>
        <h3>{{ fullName }}</h3>
        <base-badge :type="role" :caption="role.toUpperCase()"></base-badge>
      </template>
      <p>{{ infoText }}</p>
    </base-card>
  </section>
</template>

<script>
import BaseBadge from './BaseBadge';
import BaseCard from './BaseCard.vue';

export default {
  components: {
    BaseBadge,
    BaseCard
},
  props: ['fullName', 'infoText', 'role'],
};
</script>

<style scoped>
</style>
