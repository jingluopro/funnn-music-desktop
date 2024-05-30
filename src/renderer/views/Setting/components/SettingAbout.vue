<template lang="pug">
dt#about {{ $t('setting__about') }}
dd
  .p.small
    | 本软件完全免费，代码开源，开源地址：
    span.hover.underline(:aria-label="$t('setting__click_open')" @click="openUrl('https://www.jingluo.love/#readme')") hhttps://www.jingluo.love/
  .p.small
    | 软件的常见问题可转至：
    span.hover.underline(:aria-label="$t('setting__click_open')" @click="openUrl('https://www.jingluo.love/')") 常见问题
  .p.small
    strong 本软件没有客服
    | ，但我们整理了一些常见的使用问题，
    strong 仔细 仔细 仔细
    | 地阅读常见问题后，
  .p.small
    | 仍有问题可访问&nbsp;
    span.hover(:aria-label="$t('setting__click_open')" @click="openUrl('https://www.jingluo.love/')") https://www.jingluo.love
    | &nbsp;反馈

</template>

<script>
// import { ref, onBeforeUnmount } from '@common/utils/vueTools'
import { isShowPact } from '@renderer/store'
import { openUrl, clipboardWriteText } from '@common/utils/electron'

export default {
  name: 'SettingAbout',
  setup() {
    const handleShowPact = () => {
      isShowPact.value = true
    }
    return {
      openUrl,
      clipboardWriteText,
      handleShowPact,
    }
  },
}
</script>
