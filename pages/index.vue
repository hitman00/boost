<template>
  <div :class="$style.main">
    <div :class="$style.fix_box">
      <PieceBox
        date-start="2020/02/10"
        date-end="2020/02/10"
        number-liking="100"
      />
      <PieceBox
        date-start="2020/02/10"
        date-end="2020/02/10"
        number-liking="150"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: 'Pageindex',
  data: () => ({}),
}
</script>

<style lang="scss" module>
.main {
  max-width: 1000px;
  margin: 0 auto;
  margin-top: 219px;
}
</style>
