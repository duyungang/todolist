<template>
  <div id="app">
   <h1>todolist制作开始</h1>
   <hr>
 <input type="text" v-model="todo"  @keydown="doadd($event)"><button type="button" @click="addData()" >添加</button><br>
                      <!-- @keydown="doadd($event)" 是方法对象-->
<h4>正在处理</h4>
   <ul>
     <li v-for="(item,key) in list" v-if="!item.checked">
   <input type="checkbox" v-model="item.checked" @change="savalist()" > {{key}} 
   {{item.title}} -----  
    <button type="button" @click="removeDate(key)">删除</button>  
     </li>
   </ul>
   <br>

<h4>处理结束</h4>
   <ul>
     <li v-for="(item,key) in list" v-if="item.checked" >
   <input type="checkbox" v-model="item.checked" >
   {{key}} {{item.title}}  ------
    <button type="button" @click="removeDate(key)">删除</button>
     
     </li>
   </ul>
   
   
  </div>
</template>

<script>
export default {
  data:function(){
    return {
      todo:'',

      list:[
        {
          title:'',
          checked:false,
        }
      ],
    }
  },

  methods:{
    addData:function()
    {
     this.list.push(                                                //将添加的数据放入到数组中保存。
       {
       title:this.todo,
       checked:false
       }
       );                  
    },
    removeDate:function(key)
    {
      this.list.splice(key,1);                                    //删除数组中的元素
       localStorage.setItem('list',JSON.stringify(this.list))  ;  //删除后的数据保存到本地存储
    }, 
    doadd(e)
    {                                                     //方法的定义ES6的写法，e.keyCode是获取键盘的点击类型，13是回车键
      console.log(e.keyCode);
      if (e.keyCode==13){
      this.list.push(
       {
       title:this.todo,
       checked:false
            })
       }
  localStorage.setItem('list',JSON.stringify(this.list))  ;       //保存新加入的数据到本地存储
    },
    savalist(){
      localStorage.setItem('list',JSON.stringify(this.list)) ;  
    }
  }
  ,

  mounted(){   //生命周期函数  vue页面刷新时触发
var list=JSON.parse(localStorage.getItem('list'));
if (list){       //判断是否为空
  this.list=list;
}
  }

}
</script>

<style>

</style>
