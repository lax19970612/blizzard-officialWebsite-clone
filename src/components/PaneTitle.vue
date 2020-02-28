<template lang='pug'>
div.paneTitle
  h2.title
    span.HeadingText {{ HeadingText }}
    span.HeadingSubtext {{ HeadingSubtext }}
    div.HeadingIcon
      img(src='~@/assets/image/svg/next-blue.svg')
</template>

<script>
export default {
  name: 'PaneTitle',
  props: {
    HeadingText: String,
    HeadingSubtext: String
  }
}
</script>

<style>
.title {
  display: inline-flex;
  align-items: flex-end;
}

.HeadingText {
  color: #fff;
  font-size: 35.154px;
}

.HeadingSubtext {
  color: #00aeff;
  font-size: 14.4px;
  margin-left: 16px;
  transition: color 0.3s ease;
}

.HeadingSubtext:hover {
  color: #fff;
  cursor: pointer;
}

.HeadingIcon {
  width: .4em;
  height: .4em;
  margin-bottom: .57em;
}
</style>
