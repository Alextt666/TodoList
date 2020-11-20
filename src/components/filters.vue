<template>
  <div class="filters">
    <span
      v-for="filter in filters"
      :key="filter.value"
      @click="$emit('change-filter', filter.value)"
      class="filter"
      :class="{ active: selected === filter.value }"
      >{{ filter.label }}</span
    >
  </div>
</template>

<script>
export default {
  name: "filters",
  props: ["selected"],
  setup() {
    const filters = [
      { label: "全部", value: "all" },
      { label: "未完成", value: "todo" },
      { label: "已完成", value: "done" },
    ];
    return {
      filters,
    };
  },
};
</script>

<style>
/* filters部分 */
.filters {
  width: 100%;
  height: 3rem;
  color: #c0c2ce;
  margin: 2rem 0;
  font-size: 1.5rem;
  padding-left: 2.5rem;
  display: flex;
  align-items: center;
}
.filters .filter {
  padding-right: 1.5rem;
  font-size: 1em;
}
.filters .filter.active {
  color: #6b729c;
  transform: scale(1.2);
}
</style>
