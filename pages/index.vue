<template>
  <div :class="$style.main">
    <div :class="$style.item">
      <CardBox
        date-start="2020/02/10"
        date-end="2020/02/10"
        number-liking="100"
      />
    </div>
    <div :class="$style.item">
      <CardBox
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
}
</script>

<style lang="scss" module>
.main {
  max-width: 1000px;
  margin: 0 auto;
  margin-top: 219px;
}

.item {
  float: left;
  margin-right: 16px;
}
</style>
