<template>
  <input
    type="text"
    class="form-control search-input"
    placeholder="Search movie"
    :value="term"
    @input="changeHandler"
  />
</template>
<script>
export default {
  props: {
    updateTerm: {
      type: Function,
      required: true,
    },
  },
  data() {
    return {
      term: "",
    };
  },
  methods: {
    changeHandler(e) {
      this.term = e.target.value;
      this.updateTerm(this.term);
    },
  },
};
</script>
<style scoped>
.search-input {
  margin-top: 1rem;
  margin-bottom: 1.5rem;
  padding: 1.5rem;
  background-color: #fcfaf5;
  border-radius: 4px;
  box-shadow: 15px 15px 15px rgba(0, 0, 0, 0.15);
}
</style>
