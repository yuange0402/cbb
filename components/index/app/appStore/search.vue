<template>
     <div class="search">
            <el-input v-model="keyword" placeholder="请输入搜索内容"></el-input>
            <el-button @click="search" type="primary">搜索</el-button>
     </div>
</template>
<script>
export default{
    data(){
        return{
             keyword:""
        }
    },
    methods:{
       search(){ 
            console.log(this.keyword,"搜索关键字=======");
             const h = this.$createElement;

        this.$notify({
          title: '标题名称',
          message: h('div', { style: 'color: teal'},"搜索"+ this.keyword)
        });
       }
    }
   
}
</script>
<style lang="scss" scoped>

@import '../../../../assets/common.scss';
   .search{
    //    border: 3px solid red;
    //    padding: 10px;
       display: flex;
       width:480px;

   
 
   }


</style>

<style lang="scss">

    .search{
        .el-input__inner{
            border-radius: 10px 0px 0px 10px;
        }
        .el-button {
                border-radius:0px 10px 10px 0px;
        }
    }
</style>