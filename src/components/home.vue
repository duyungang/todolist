<template>
<!--所有的内容要包含在根标签下-->
    <div>
  <h1>我是主页，yo!</h1>
  <button type="button" @click="run()">执行run方法</button>
  <v-life></v-life>
    </div>
</template>
<script>

import life from './life.vue';
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
    },
    components:{
        'v-life':life
    }

}
</script>


<style  scoped>
h1{
    color: red;
}
    
</style>


