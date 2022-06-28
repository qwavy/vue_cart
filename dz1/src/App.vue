<template>
  <head-header/>
  <main-content/>
  <profuct-form/>
  <add-cart/>
</template>
<script>
import HeadHeader from './components/HeadHeader.vue'
import MainContent from './components/MainContent.vue'
import AddCart from './components/AddCart.vue'
export default {
  components:{
    HeadHeader,
    MainContent,
    AddCart
  }
}
</script>