<template>
     <div class="accountBalance">
            <el-breadcrumb separator-class="el-icon-arrow-right" class="ybread">
               <el-breadcrumb-item :to="{ path: '/' }">首页</el-breadcrumb-item>
               <el-breadcrumb-item>活动管理</el-breadcrumb-item>
               <el-breadcrumb-item>活动列表</el-breadcrumb-item>
               <el-breadcrumb-item>活动详情</el-breadcrumb-item>
           </el-breadcrumb>
           <div class="box">
               <div class="header">
                    <span>
<svg t="1594793876555" class="headerIcon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="4422" width="25" height="25"><path d="M789.8112 234.1888C715.5712 159.9488 616.96 119.0912 512 119.0912s-203.5712 40.8576-277.8112 115.0976S119.0912 407.04 119.0912 512s40.8576 203.5712 115.0976 277.8112S407.04 904.9088 512 904.9088s203.5712-40.8576 277.8112-115.0976S904.9088 616.96 904.9088 512s-40.8576-203.5712-115.0976-277.8112z m-68.1984 242.3808l-78.6432 76.6976L661.504 661.504c2.3552 13.9264-3.1744 27.648-14.6432 35.9424-6.4512 4.7104-14.0288 7.0656-21.6064 7.0656-5.8368 0-11.6736-1.4336-17.1008-4.3008l-97.28-51.0976-97.28 51.0976c-12.4928 6.5536-27.3408 5.5296-38.7072-2.7648-11.3664-8.2944-16.9984-22.1184-14.6432-35.9424L378.88 553.1648l-78.6432-76.6976c-10.1376-9.8304-13.7216-24.2688-9.3184-37.6832 4.4032-13.4144 15.7696-23.04 29.696-24.9856l108.6464-15.7696 48.64-98.5088c6.2464-12.6976 18.8416-20.48 32.9728-20.48 14.1312 0 26.7264 7.8848 32.9728 20.48l48.64 98.5088 108.6464 15.7696c13.9264 2.048 25.3952 11.5712 29.696 25.088 4.5056 13.312 0.9216 27.7504-9.216 37.6832z" p-id="4423" fill="#ffffff"></path></svg>
              账户积分
                     </span>
                          <el-tooltip  placement="bottom" effect="light">
                             <div slot="content"> 
                                  平台上的部分类目只支持积分消费。积分<br>
                                  主要通过充值、参与平台活动等方式获得<br>
                                  ，不能提现。10 积分 = 1 元。
                             </div>
                            <svg t="1594794379850" class="request" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="5380" width="20" height="20"><path d="M511.998-0.004C229.228-0.004 0 229.228 0 511.998c0 282.772 229.228 512.006 511.998 512.006C794.772 1024.004 1024 794.77 1024 512 1024 229.23 794.774-0.004 511.998-0.004zM561.686 807.444c0 14.138-11.458 25.602-25.6 25.602l-76.8 0c-14.136 0-25.598-11.462-25.598-25.602l0-76.798c0-14.142 11.462-25.604 25.598-25.604l76.8 0c14.14 0 25.6 11.46 25.6 25.604L561.686 807.444zM688.588 455.06c-10.29 14.672-33.646 33.368-62.886 56.162l-32.404 22.362c-15.738 12.208-29.696 26.42-34.858 42.692-1.764 5.544-3.086 14.656-3.976 24.496-0.448 4.952-4.878 15.054-15.232 15.054-25.37 0-73.72 0-83.34 0-13.546 0-15.966-10.61-15.74-15.8 1.5-34.016 4.616-64.216 18.476-80.474 28.06-32.9 91.908-73.852 91.908-73.852 9.72-7.336 17.59-15.31 23.542-24 10.82-14.92 19.796-31.304 19.796-49.214 0-20.584-6.018-39.348-18.094-56.332-12.034-16.916-34.078-25.392-66.02-25.392-31.444 0-53.734 10.436-66.874 31.3-9.706 15.416-15.818 29.588-18.348 45.01-0.9 5.458-4.4 16.954-16.066 16.954-24.65 0-70.094 0-81.282 0-17.308 0-21.118-11.216-20.618-16.622 6.266-68.138 32.892-114.692 79.972-144.586 32.014-20.582 71.4-30.91 118.12-30.91 61.39 0 112.35 14.634 152.978 43.944 40.556 29.27 60.892 72.642 60.892 130.15C718.538 401.22 706.178 430.918 688.588 455.06z" p-id="5381" fill="#ffffff"></path></svg>
                          </el-tooltip>
               </div>
               <div class="body">154543</div>
               <div class="footer">
                    <nuxt-link to="/finance/accountBalance/recharge">
                       <el-button type="danger" round >充值</el-button> 
                    </nuxt-link>
                    <el-button type="danger" round>明细</el-button>
               </div>
           </div>
     </div>
</template>

<script>
export default {

}
</script>
<style lang="scss" scoped>
    @import '../../../../assets/common.scss';
     .accountBalance{
          // border: 1px solid red;

          .box{
               width:486px; 
               height:212px;
               // border: 1px solid red;
               background-image: url(/static/img/finance.png);
               background-size: 100% 100%;
               padding: 20px;
               display: flex;
               flex-direction: column;
               justify-content: space-between;

               .header,.body,.footer{
                    // border: 1px solid blue;
               }

               .header{
                    font-size:18px;
                    font-family:Microsoft YaHei;
                    font-weight:400;
                    color:rgba(224,238,255,1);
                    display: flex;
                    justify-content: space-between;

                    .headerIcon{
                         transform: translateY(5px);
                    }

                    .request{
                         transform: translateY(5px);
                    }
               }

               .body{
                    font-size:48px;
                    // font-family:DIN Next W1G;
                    font-family:-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
                    font-weight:500;
                    color:rgba(255,255,255,1);
               }


               .footer{
                    button{
                         color: #F43B61;
                        padding:8px 50px;
                        background-color: #fff;
                    }
               }
          }
     }
</style>

<style>

</style>