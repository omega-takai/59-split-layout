<template lang="pug">
  section(:class="$style.section")
    div(
      v-for="val in 59"
      :key="val"
      v-text="val"
      :class="$style.item"
    )
    div(:class="$style.hr")
    div(:class="$style.wrapper")
      section(:class="[$style.section2col, $style.height7]")
        div(:class="[$style.split2, $style.height7]" v-text="'split2'")
        div(:class="[$style.split2, $style.height3]" v-text="'split2'")
        div(:class="[$style.split2, $style.height3]" v-text="'split2'")
</template>

<script>
export default {
  name: 'Base59System',
}
</script>

<style lang="sass" module>
$_itemSize: 10px
$_width: $_itemSize * 59
$_outerPadding: 15px

@mixin _itemStyle()
  flex: 0 0 auto
  color: colors('white')
  line-height: 1

.height1
  height: $_itemSize

.height3
  height: $_itemSize * 3

.height5
  height: $_itemSize * 5

.height7
  height: $_itemSize * 7

.section
  display: flex
  flex-wrap: wrap
  width: 100%
  max-width: $_width
  padding: $_outerPadding
  box-sizing: content-box
  background-color: colors('white')

  .item
    @include _itemStyle()
    width: $_itemSize
    height: $_itemSize
    &:nth-of-type(even)
      background-color: colors('fontSub')
    &:nth-of-type(odd)
      background-color: colors('inverted')

  .hr
    flex: 0 0 auto
    width: $_width
    height: $_itemSize
    background-color: colors('white')

  .wrapper
    flex: 1 1 100%

.section2col
  display: flex
  flex-flow: column wrap
  justify-content: space-between
  align-content: space-between
  width: 100%

  .split2
    @include _itemStyle()
    width: ($_width - $_itemSize) / 2
    padding: $_itemSize
    background-color: colors('fontSub')
</style>
