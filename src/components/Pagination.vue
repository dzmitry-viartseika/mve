<template>
    <div class="pagination">

    </div>
</template>

<script>
export default {
  name: 'Pagination',
};
</script>

<style scoped lang="scss">

  @import "../assets/scss/core";

  .pagination {
    font-size: 16px;
    display: flex;
    justify-content: center;
    &__link {
      text-decoration: none;
      color: $color-black;
      padding: 5px;
    }
  }
</style>
