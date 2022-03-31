<template>
  <v-text-field
    v-model="search"
    @focus="searchClosed = false"
    @blur="searchClosed = true"
    class="expanding-search mt-1"
    :class="{ closed: searchClosed && !search }"
    placeholder="Search"
    filled
    dense
    clearable
    prepend-inner-icon="mdi-magnify"
  ></v-text-field>
</template>

<script>
export default {
  data() {
    return {
      searchClosed: true,
      search: null,
    };
  },
};
</script>

<style lang="sass">
.expanding-search
  .v-input__slot
    cursor:pointer
    &:before, &:after
      border-color:transparent
  &.closed
    max-width:45px
    .v-input__slot
      background:transparent
</style>
