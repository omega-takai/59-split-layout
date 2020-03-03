<template lang="pug">
  section(:class="$style.section")
    div(
      v-for="val in 59"
      :key="val"
      v-text="val"
      :class="$style.item"
    )

    section(:class="[$style.grid2col, $style.wrapper]")
      div(
        :class="$style.gridItem"
        v-for="val in 3"
        v-text="'split2'"
        :key="'grid-item-' + val"
      )
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
  margin:
    top: $_outerPadding
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

  .wrapper
    flex: 1 1 100%

.grid2col
  margin: $_itemSize 0
  display: grid
  gap: $_itemSize
  grid-template:
    areas: 'first second' 'first third'
    columns: 1fr 1fr
    rows: ($_itemSize * 3) ($_itemSize * 3)

  .gridItem
    padding: $_itemSize
    color: colors('white')
    line-height: 1
    background-color: colors('fontSub')
    &:nth-of-type(1)
      grid-area: first
    &:nth-of-type(2)
      grid-area: second
    &:nth-of-type(3)
      grid-area: third
</style>
