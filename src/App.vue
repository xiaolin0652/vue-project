<template>
   <div>
    <Header></Header>
    <div class="container">
      <Add :addcomment='addcomment'></Add>
      <List :comments='comments' :deleteCom='deleteCom'></List>
    </div>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Add from './components/Add.vue'
import List from './components/List.vue'
export default {
  components: { 
      Header ,
      Add,
      List
      },
  name: '',
  data(){
    return {
      comments:[
        {id:'001',username:'肖战',content:'Vue真不错'},
        {id:'002',username:'王一博',content:'Vue真帅'},
        {id:'003',username:'李现',content:'Vue好'},
      ]
    }
  },
  methods:{
    addcomment(obj){
      this.comments.unshift(obj)
    },
    deleteCom(index){
      this.comments.splice(index,1)
    }
  }
}
</script>

<style scoped>

</style>
