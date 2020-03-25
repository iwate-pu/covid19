<template>
  <div  class="TopBarNotice">
    このサイトはメンテナンスされていません。最新情報は
    <a href="https://www.pref.iwate.jp/kurashikankyou/iryou/kenkou/jouhou/1026260.html">新型コロナウイルス感染症に関する情報《岩手県》</a>
    または
    <a
      href="https://covid19-iwate.netlify.com/"
      target="_blank"
      rel="noopener noreferrer"
    >岩手県　非公式　コロナウイルス感染症対策サイト</a>をご覧ください。
  </div>
</template>

<style lang="scss">
.TopBarNotice {
  position: fixed;
  top: 0;
  left: 0;
  font-size: 12px;
  z-index: 1;
  width: 100%;
  height: 20px;
  text-align: center;
  background-color: #ffe200;
  color: #4d4d4d;
  line-height: 20px;
  opacity: 0.9;

  // mobile view
  @include lessThan($small) {
    height: 40px;

    a {
      display: block;
    }
  }
}
</style>

<script>
export default {
  name: 'TopBarNotice',
  props: {
    value: {
      type: String,
      required: false,
      default: ''
    }
  },
  computed: {
    isDevelopmentMode: () => {
      if (process && process.env && process.env.GENERATE_ENV) {
        return process.env.GENERATE_ENV === 'development'
      }
      return false
    }
  }
}
</script>
