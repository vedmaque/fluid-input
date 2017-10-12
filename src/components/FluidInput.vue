<template>
  <div class="input__wrapper">
    <div class="input">
      <input type="text" v-model="inputValue" placeholder="Amount">
    </div>
    <div class="input__shadowValue" :class="shadowClass"><span class="shadow">{{ inputValue }}</span><span class="currency">$</span></div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      inputValue: ''
    }
  },
  computed: {
    shadowClass () {
      return this.inputValue === '' ? '_hidden' : '_visible'
    }
  }
}
</script>

<style lang="scss">
  input {
    border: 0px solid #000;
    outline: none;
    font-family: inherit;
    font-size: inherit;
    color: inherit;
    padding: 0;
  }
  .input {
    display: flex;
    position: relative;
    z-index: 1;
    width: 100%;
    height: 100%;

    &__wrapper {
      position: relative;
      width: 140px;
      height: 30px;
    }
    & input {
      border-bottom: 1px solid #BDBDBD;
      width: 100%;
      height: 100%;
      padding-right: 14px;
      transition: all .3s ease-in-out;
      background: transparent;
      &:focus {
        border-color: #000;
      }
      &::placeholder {
        opacity: .5;
      }
    }

    &__shadowValue {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      display: flex;
      align-items: center;
      transition: all .3s ease-in-out;
      & span {
        &.shadow {
          visibility: hidden;
          max-width: 100%;
          overflow: hidden;
        }
        &.currency {
          margin-left: 5px;
        }
      }
      &._hidden {
        opacity: 0;
        transform: translateX(-5px);
        transition: none;
      }
    }
  }
</style>
