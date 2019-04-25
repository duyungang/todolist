<template>
    <div id="life">
        <h4>{{msg}}</h4>

        <button type="button" @click="show()">生命周期执行方法</button>
    </div>
</template>


<script>
export default {
    data:function(){
        return {
msg:'我是一个生命周期函数组件'
        }
    },
    methods:{
        show(){
            this.msg='改变了';
        }
    },
  beforeCreate(){
      console.log("实例刚开始创建");
  },
  created(){
    console.log('实例已经创建完毕');
  },
  beforeMount(){
     console.log('模板编译开始！');
  },
  mounted(){
     console.log('模板编译完成！');
  },
  beforeUpdate(){
     console.log('数据更新开始！');
  },
  updated(){
      console.log('数据更新结束');
  },
  beforeDestroy(){
      console.log('实例销毁之前');
  },
  destroyed(){
      console.log('实例销毁之后');
  }

    
}
</script>


<style>

</style>


