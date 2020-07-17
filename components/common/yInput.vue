<template>

    <!-- 组件使用
    1 使用组件的话不需要给组件绑定v-model,直接可以通过 this.refs['param'].value 操作绑定的
     -->
     <div class="inputW" >
         <input @change="ychange" @focus="yfocus" @blur="yblur" @input="emitInput" :class="{'focus':focus,'input':true}" type="text" :placeholder="placeholder" v-model="value">
     </div>
</template>

<script>
export default {
      data(){
           return{
               value:"",
               focus:false
           }
      },
      props:{
          placeholder:{
               type:String,
               default:"请输入内容"
          }
      },
      methods:{
          yfocus(){
              console.log("kkkkkkk")
              this.focus = true;
          },

          yblur(){
              this.focus = false;
          },

          emitInput(e){
              console.log("iput",e)
              this.$emit("input",e.target.value)
          },

          ychange(e){
            //    console.log(e.target.value);
            //    this.$emit("change",e.target.value)

          }
      }

}

</script>
<style lang="scss" scoped>
@import '../../assets/common.scss';
   .inputW{
        width: 100%;
        // border: 1px solid red;
   }

     .input{ 
        // border: none;
        border: none;
        border-bottom: 1px solid $underlineColor;
        padding: 5px;
        text-align: left;
        outline: none;
        width: 100%;

     }

     .focus{
          border-bottom: 2px solid $theamColor;
     }
</style>
<style>

</style>