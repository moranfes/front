<template>
  <div class="app-container">
    <router-view v-if="isReload"></router-view>
  </div>
</template>

<script>
export default {
  name: "App",

  provide() {
    return {
      reload: this.reload
    };
  },

  data() {
    return {
      isReload: true
    };
  },

  methods: {
    reload() {
      this.isReload = false;

      this.$nextTick(() => {
        this.isReload = true;
      });
    }
  }
};
</script>

<style lang="less" scoped>
</style>

