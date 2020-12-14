<template>
   <div>
    <Header></Header>
    <div class="container">
      <Add></Add>
      <List></List>
    </div>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Add from './components/Add'
import List from './components/List'
export default {
  components: { 
      Header ,
      Add,
      List
      },
  name: '',
}
</script>

<style scoped>

</style>
