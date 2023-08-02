<template>
  <div class="">
    <h2 class="pb-3">Dashboard</h2>
    <ChartComp />
  </div>
</template>

<script>
import ChartComp from '@/components/ChartComp.vue';
export default {
  name: 'DashboardView',
  components: {
    ChartComp,
  },
  data() {
    return {

    };
  },
  methods: {

  }
}
</script>

<style lang="scss" scoped></style>
