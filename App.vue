<template>
  <div id="app">
      <input type="text" v-model="text">
      <button @click="handleClick">提交</button>
      <ul class="todu-list">
        <li v-for="(item,index) in list" :key="index" @click="removeItem(index)">
          {{item}}
        </li>
      </ul>
  </div>
</template>

<script>
  export default {
  data(){
    return({
      list:[
        '第一条数据',
        '第二条数据',
        '第三条数据',
      ],
      text:''
    })
  },
  methods:{
    handleClick(){
      // console.log(this.text);
      this.list.push(this.text);
      this.text=""
    },
    removeItem(index){
      this.list.splice(index,1)
    }
  }
}
</script>

<style>
#app{
  width: 400px;
  height: 300px;
  padding-top:20px; 
  font-size: 24px;
  margin: 0 auto;
  border-radius: 20px;
  background-color: aquamarine;
}
#app input{
  width: 150px;
  height: 20px;

  margin-left: 100px;
   border-radius: 5px;

}
#app button{
  width: 80px;
  height: 30px;
  margin-left: 20px;
  background-color: coral;
  border-radius: 5px;

}
.todu-list{
  text-align: center;
  list-style: none;
  line-height: 45px;
}
</style>
