<template>
  <div class="wrapper-search">
    <div class="search">
      <div class="search-icon">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="24"
          height="24"
          viewBox="0 0 24 24"
          fill="none"
          stroke="currentColor"
          stroke-width="2"
          stroke-linecap="round"
          stroke-linejoin="round"
          class="feather feather-search"
        >
          <circle cx="11" cy="11" r="8"></circle>
          <line x1="21" y1="21" x2="16.65" y2="16.65"></line>
        </svg>
      </div>
    </div>

    <input type="text" :placeholder="placeholder" v-model="search" />
  </div>
</template>

<script>
export default {
  props: {
    value: {
      type: String,
      required: true,
    },
    placeholder: {
      type: String,
      default: "Search",
    },
  },
  data() {
    return { search: this.value };
  },
  watch: {
    search(val) {
      this.$emit("search", val);
    },
  },
};
</script>

<style scoped>
svg {
  color: #e7e6e6;
}

.wrapper-search {
  position: relative;
}

.search {
  top: 0px;
  bottom: 0px;
  left: 0px;
  position: absolute;
}

.search-icon {
  display: flex;
  align-items: center;
  height: 100%;
  padding-left: 16px;
  padding-right: 16px;
}

input {
  padding: 16px 16px 16px 56px !important;
  margin-bottom: 0px;
  border-radius: 30px;
  color: #92959c;
  font-size: 16px;
  min-width: 400px;
  height: auto;
}
</style>