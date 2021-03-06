<template lang="pug">
  doc-view(v-bind:doc="doc")
    component-example(header="Selects")
      div
        v-select(
          v-bind:options="options",
          id="test",
          label="Testing",
          name="test",
          v-model="input"
        )
        div {{ input }}
      div
        v-select(
          v-bind:options="options",
          id="test4",
          label="Testing4",
          name="test4",
          multiple,
          v-model="multiple"
        )
        div {{ multiple }}
    component-example(header="Inputs")
      div
        v-text-input(
          id="test2",
          name="test2",
          label="Testing 2"
          v-model="text"
        )
        div {{ text }}
      div
        v-text-input(
          id="test3",
          name="test3",
          label="Testing 3",
          placeholder="Testing 3"
        )
    component-example(header="Radios")
      v-radio(
        id="test5",
        name="test5",
        label="Testing 5"
      )
      v-radio(
        id="test6",
        name="test5",
        label="Testing 6",
        gap
      )
      v-radio(
        id="test62",
        name="test52",
        label="Testing 62",
        gap,
        checked,
        disabled
      )
      v-radio(
        id="test61",
        name="test54",
        label="Testing 61",
        disabled,
        checked
      )
      v-radio(
        id="test71",
        name="test5",
        label="Testing 71",
        disabled
      )
    component-example(header="Checkboxes")
      v-checkbox(
        id="test7",
        name="test7",
        label="Testing 7"
      )
      v-checkbox(
        id="test8",
        name="test8",
        label="Testing 8",
        filled
      )
      v-checkbox(
        id="test9",
        name="test9",
        label="Testing 9",
        indeterminate
      )
      v-checkbox(
        id="test10",
        name="test10",
        label="Testing 10",
        disabled
      )
      v-checkbox(
        id="test10",
        name="test10",
        label="Testing 10",
        checked,
        disabled
      )
    div(slot="markup")
      markup(lang="html")
        |&lt;v-select v-bind:options="options"&gt;
        |   ...
        |&lt;/v-select&gt;
        |&nbsp;
        |&lt;v-text-input label="Label" value="yes" id="terms" name="terms" v-model="text"&gt;
        |   ...
        |&lt;/v-text-input&gt;
        |&nbsp;
        |&lt;v-radio gap indeterminate&gt;
        |   ...
        |&lt;/v-radio&gt;
        |&nbsp;
        |&lt;v-checkbox name="check" id="check"&gt;
        |   ...
        |&lt;/v-checkbox&gt;
      markup(lang="js")
        |data () {
        |   return {
        |     text: '',
        |     options: [
        |       { value: 1, text: 'One' },
        |       { value: 2, text: 'Two' },
        |       { value: 3, text: 'Three' },
        |     ]
        |   }
        |}
</template>

<script>
  export default {
    data () {
      return {
        doc: {
          title: 'Form Inputs',
          desc: 'Form components are used for collecting user provided information.',
          params: [
            [
              '<code>v-select</code>',
              '',
              'Base component'
            ],
            [
              '<code>defaultText</code>',
              'Sets default option text',
              'Required: Select...'
            ],
            [
              '<code>multiple</code>',
              'Sets the multiple attribute',
              'Default: false'
            ],
            [
              '<code>options</code>',
              'The options array',
              'Allowed object properties: [id, text]'
            ],
            [
              '<code>v-text-input</code>',
              '',
              'Base component'
            ],
            [
              '<code>v-model</code>',
              '',
              'Required: false'
            ],
            [
              '<code>type</code>',
              'Sets the type attribute (v-text-input only)',
              "Default: text"
            ],
            [
              '<code>v-radio</code>',
              '',
              'Base component'
            ],
            [
              '<code>v-model</code>',
              '',
              'Allowed types: [String, Number, Boolean]'
            ],
            [
              '<code>gap</code>',
              'Applies the gap class',
              'Default: false'
            ],
            [
              '<code>v-checkbox</code>',
              '',
              'Base component'
            ],
            [
              '<code>v-model</code>',
              '',
              'Required: false'
            ],
            [
              '<code>filled</code>',
              'Applies the filled class',
              'Default: false'
            ],
            [
              '<code>gap</code>',
              'Applies the gap class',
              'Default: false'
            ],
            [
              '<code>indeterminate</code>',
              'Applies the indeterminate class',
              'Default: false'
            ],
            [
              '<strong>All Components</strong>',
              '',
              ''
            ],
            [
              '<code>disabled</code>',
              'Sets the disabled attribute',
              "Default: ''"
            ],
            [
              '<code>label</code>',
              'Sets the label text',
              "Default: ''"
            ],
            [
              '<code>id</code>',
              'Sets the input id',
              "Default: ''"
            ],
            [
              '<code>name</code>',
              'Sets the label text',
              "Default: ''"
            ],
            [
              '<code>placeholder</code>',
              'Sets the placeholder text',
              "Default: ''"
            ]
          ]
        },
        input: null,
        multiple: ['2'],
        options: [
          {
            value: 1,
            text: 'Option 1'
          },
          {
            value: 2,
            text: 'Option 2'
          },
          {
            value: 3,
            text: 'Option 3'
          }
        ],
        text: ''
      }
    },

    mounted () {
      this.$emit('view', this.meta())
    },

    preFetch () {
      return this.methods.meta()
    },

    methods: {
      meta () {
        return {
          title: 'Form Input Components | Vuetify.js',
          h1: 'Form Inputs',
          description: 'Form input components for Vuetify Framework',
          keywords: 'vuetify, form, components'
        }
      }
    }
  }
</script>

<style lang="stylus" scoped>
  .component-example
    justify-content: space-between
    flex-wrap: wrap
    
    > *
      margin: 2rem 0
</style>