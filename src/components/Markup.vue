<template lang="pug">
  div(class="markup")
    pre
      code(v-bind:class="lang" ref="code")
        slot
</template>

<script>
  import hljs from 'highlight.js/lib/highlight.js'

	export default {
    props: {
      lang: String
    },

		mounted () {
			hljs.highlightBlock(this.$refs.code)
		}
	}
</script>

<style lang="stylus">
  @import '../stylus/settings/_variables'
  
  .tabs
    .markup
      margin: 2rem 0
      
  .markup
    background: rgba(0, 0, 0, .03)
    margin: 2rem -4rem
    font-size: 1.2rem
    transition: .3s ease-out
    word-break: break-all
    overflow: hidden
    
    &:hover
      background: rgba(0, 0, 0, .06)
    
    pre, code
      background: transparent
      width: 100%
      display: block
      
    code
      font-weight: 600 !important
      position: relative
      padding: 3rem 4rem
      
      &:before
        display: none
      
      &:after
        color: #fff
        position: absolute
        font-size: .7rem
        top: 0
        right: 1rem
        background: rgba(#444, .3)
        padding: .1rem .5rem
        font-weight: 100
        letter-spacing: 2px
        transition: $primary-transition
        
      &.html
        &:after
          content: 'html'
      &.js
        &:after
          content: 'javascript'
      &.cli
        &:after
          content: 'cli'
      &.scss
        &:after
          content: 'scss'
      &.stylus
        &:after
          content: 'stylus'
    
    .hljs
      color: $theme.secondary
      
      .hljs-tag, .hljs-variable
        color: $purple.lighten-1
      
      .hljs-attr, .hljs-keyword
        color: $theme.primary
        
      .hljs-string, .hljs-literal, .hljs-number
        color: $red.lighten-2
    
    
    @media screen and (max-width: $grid-breakpoints.sm)
      margin: 2rem -1rem
      
      code
        padding: 3rem 1rem
</style>