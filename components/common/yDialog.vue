<template>
    <el-dialog
        :title="title"
        :visible.sync="show"
        :width = "ywidth"
        
        > 
      
        <div>
             <slot name = "msg"></slot>
        </div>
        <span slot="footer" class="dialog-footer">
            <slot name = "footer"></slot>
        </span>
    </el-dialog>
</template>

<script>
  export default {
    data() {
      return {
        show:false,
      };
    },
    props:{
      title:{
         type:String,
         default:"提示"
      },
      ywidth:{
         type:String,
         default:"30%"
      }
    },
    methods: {
    //   handleClose(done) {
    //     this.$confirm('确认关闭？')
    //       .then(_ => {
    //         done();
    //       })
    //       .catch(_ => {});
    //   }
    }
  };
</script>
<style lang="scss" scoped>
  .el-dialog{
      border-radius: 10px;
      overflow: hidden;
  }

  .el-dialog__header{
      border-bottom: 1px solid $underlineColor;
  }

  .el-dialog__footer{
      background-color: #E9E9E9;
      height:60px;
  }

  .dialog-footer{
    //    border: 1px solid red;
       width: 100%;
       height: 100%;
       display: inline-block;
       display: flex;
       justify-content: space-between;
       align-items: center;
  }

</style>