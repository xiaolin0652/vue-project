<template>
  <div class="col-md-4">
        <form class="form-horizontal">
          <div class="form-group">
            <label>用户名</label>
            <input type="text" class="form-control" placeholder="用户名" v-model="username">
          </div>
          <div class="form-group">
            <label>评论内容</label>
            <textarea class="form-control" rows="6" placeholder="评论内容" v-model="content"></textarea>
          </div>
          <div class="form-group">
            <div class="col-sm-offset-2 col-sm-10">
              <button @click='addcom' type="button" class="btn btn-default pull-right">提交</button>
            </div>
          </div>
        </form>
      </div>
</template>

<script>
export default {
  name: '',
  props:['comments','addcomment'],
  data(){
    return {
      username:'',
      content:''
    }
  },
  methods:{
    addcom(){
      //获取数据
      const {username,content}=this
      //判断用户输入是否合法
      if(username.trim() && content.trim()){
        //将用户输入整理为对象 放入到App组件的数据中
        let obj={id:Date.now(),username,content}
        //将数据给到父组件 一般会让父组件定义函数  子组件通过传参形式传过去
        this.addcomment(obj)
      }else{
        alert('请输入合法的用户名与内容')
      }
      //提交后清除输入框
      this.username='',
      this.content=''
    }
  }
}
</script>

<style scoped>

</style>

