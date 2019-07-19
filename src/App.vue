<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>




export default {
  name: 'App',
  components: {

  },
  data() {
    return {
      loading: true,
    };
  },
};
</script>

<style lang="scss">

@import "../src/assets/scss/core";

.header {
  padding: 0 50px;
  width: 100%;
  height: 40px;
  background: $color-spindle;
    @media screen and (max-width: 1260px) {
      & {
        height: 120px;
        padding-top: 10px;
      }
  }
  @media screen and (max-width: 510px) {
    & {
      padding: 10px;
    }
  }
    &-row {
      height: 100%;
      display: flex;
      justify-content: space-between;
      flex-direction: row;
      align-items: center;
        @media screen and (max-width: 1260px) {
          & {
            flex-direction: column;
            &__user {
              height: 30px;
            }
          }
      }
      &__logo {
        font-size: 24px;
        font-weight: bold;
        &-link {
          text-decoration: none;
          color: $color-black;
        }
      }
    }
}
</style>
