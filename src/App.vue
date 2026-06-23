<script setup>
const message = 'Hello world'

const rawHtml = '<div><h1>Title</h1><span style="color: red">This should be red.</span></div>'

const buttonId = 'btnId'
const buttonClass = 'btnClass'
const isDisabled = false

const objectOfAttrs = {
  id: 'container',
  class: 'wrapper',
  style: {
    color: 'blue',
  },
}
</script>

<template>
  <h1>Syntax</h1>
  <p>Message: {{ message }}</p>

  <span v-html="rawHtml"></span>

  <button v-bind:id="buttonId">Click</button>
  <br />
  <button :id="buttonId" :class="buttonClass" :disabled="isDisabled">Click</button>
  <br />
  <button v-bind="objectOfAttrs">Click here!!!</button>
</template>
