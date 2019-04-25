<template>
<!--所有的内容要包含在根标签下-->
    <div>
  <h1>我是主页，yo!</h1>
  <button type="button" @click="run()">执行run方法</button>
    </div>
</template>
<script>


export default {
    data:function(){
        return {
      msg:'欢迎来到主页，哈哈！'
        }
    },
    methods:
    {
        run(){
            alert(this.msg);
        }
    }

}
</script>


<style  scoped>
h1{
    color: red;
}
    
</style>


