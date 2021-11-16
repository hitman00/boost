<template>
  <div :class="$style.boost_main">
    <div
      :class="[$style.add_box, show ? $style.active : '']"
      @click="show = false"
    >
      +
    </div>
    <div :class="$style.first_box" @click="show = true">
      <div :class="$style.btn">BOOST</div>
      <div :class="$style.text">
        LIKING <span>{{ numberLiking }}</span>
      </div>
    </div>
    <transition name="fade">
      <div v-if="show" :class="$style.create_boost">
        <div :class="$style.title"><span>CREATE BOOST</span></div>
        <div :class="$style.dash">date Period</div>
        <div :class="$style.date_title">Pick date Range:</div>
        <div :class="$style.date">
          <div :class="$style.date_start">{{ dateStart }}</div>
          TO
          <div :class="$style.date_end">{{ dateEnd }}</div>
        </div>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'PieceBox',
  props: {
    dateStart: {
      type: String,
      default: '',
    },
    dateEnd: {
      type: String,
      default: '',
    },
    numberLiking: {
      type: String,
      default: '',
    },
  },
  data: () => ({
    show: false,
  }),
}
</script>

<style lang="scss" module>
.boost_main {
  position: relative;
  background: #fff;
  border: 1px solid #eaeaea;
  border-radius: 8px;
  display: inline-block;
  margin-right: 16px;
}

.add_box {
  position: absolute;
  z-index: -1;
  background: #fff;
  top: -10px;
  border: 1px solid #eaeaea;
  border-radius: 8px 8px 0px 0px;
  transition: all 0.4s ease;
  color: #4f5bd5;
  font-size: 26px;
  padding: 4px 107.5px;
  margin: 0 12px;
  &:hover {
    top: -40px;
  }
  &.active {
    background: #4f5bd5;
    color: #fff;
    top: -40px;
    cursor: pointer;
  }
}

.first_box {
  padding: 24px 16px;
}

.btn {
  padding: 6px 12px;
  color: #ccd0de;
  border: 1px solid #ccd0de;
  border-radius: 13px;
  display: inline-block;
}

.text {
  color: #3c3c3c;
  margin-top: 17px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  span {
    text-align: right;
    color: #3c3c3c;
    font-size: 30px;
    font-weight: bold;
    margin-left: 120px;
  }
}

.create_boost {
  position: absolute;
  top: 0;
  width: 100%;
  padding-bottom: 178px;
  border: 1px solid #eaeaea;
  border-radius: 8px;
  background: #fff;
  animation: test 1s ease;
  z-index: 2;
}

@keyframes test {
  from {
    padding-bottom: 0px;
  }
  to {
    padding-bottom: 178px;
  }
}

.title {
  margin: 24px 0;
  text-align: center;
  span {
    display: inline-block;
    color: #4f5bd5;
    background: #4f5bd51f;
    padding: 6px 12px;
    border-radius: 13px;
    font-size: 12px;
    font-weight: 600;
  }
}

.dash {
  color: #a6acba;
  font-size: 12px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  &:before,
  &:after {
    border-bottom: 2px dashed #a6acba;
    content: '';
    width: 34%;
  }
}

.date {
  font-size: 12px;
  color: #3c3c3c80;
  display: flex;
  justify-content: space-between;
  margin: 0 35px;
}

.date_title {
  font-size: 12px;
  text-align: center;
  margin-top: 24px;
  margin-bottom: 16px;
}

.date_start,
.date_end {
  font-size: 14px;
  color: #3c3c3c;
  border-bottom: 1px solid #707070;
}

:global {
  .fade-enter-active,
  .fade-leave-active {
    transition: opacity 0.8s ease;
  }
  .fade-enter,
  .fade-leave-to {
    opacity: 0;
  }
}
</style>
