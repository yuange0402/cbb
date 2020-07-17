<template>

<div class="platformOrder">
      <el-breadcrumb separator-class="el-icon-arrow-right" class="ybread">
            <el-breadcrumb-item :to="{ path: '/' }">首页</el-breadcrumb-item>
            <el-breadcrumb-item>活动管理</el-breadcrumb-item>
            <el-breadcrumb-item>活动列表</el-breadcrumb-item>
            <el-breadcrumb-item>活动详情</el-breadcrumb-item>
      </el-breadcrumb>
     
      <div class="ybox">
                  <div class="btnW">
                        <el-button type="primary" class="yprimary">充值</el-button>
                        <el-button >应用采购</el-button>
                  </div>
                  <el-table
                        :data="tableData"
                        stripe
                        style="width: 100%; margin-top:20px;">
                        <el-table-column
                              prop="date"
                              label="日期"
                              width="180">
                        </el-table-column>
                        <el-table-column
                              prop="name"
                              label="姓名"
                              width="180">
                        </el-table-column>
                        <el-table-column
                              prop="address"
                              label="地址">
                        </el-table-column>
                  </el-table>

                  <div class="pagination">
                        <el-pagination
                              background
                              layout="prev, pager, next"
                              :total="1000">
                        </el-pagination>
                  </div>
      </div>
</div>
</template>

<script>
  export default {
    data() {
      return {
        tableData: [{
          date: '2016-05-02',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄'
        }, {
          date: '2016-05-04',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1517 弄'
        }, {
          date: '2016-05-01',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1519 弄'
        }, {
          date: '2016-05-03',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1516 弄'
        }]
      }
    }
  }
</script>
<style lang="scss" scoped>
        .pagination{
              text-align: center;
              margin-top: 50px;

              .btnW{
                    margin-bottom:50px;
              }
        }
</style>