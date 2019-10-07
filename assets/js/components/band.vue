<template>
<div>
  <h1 class="page-header">Bands</h1>
  <h1>Biba</h1>

  <h1>Boba</h1>


</div>
</template>

<script charset="utf-8">
export default {
  data() {
    return {
      bands: []
    };
  },

  created() {
    this.fetchData();
  },

  watch: {
    $route: "fetchData"
  },

  methods: {
    fetchData: function() {
      let req = $.getJSON("/api/bands");
      req.done(data => {
        this.bands = data;
      });
    }
  }
};
</script>
