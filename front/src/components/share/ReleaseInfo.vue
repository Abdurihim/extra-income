<style lang="less" rel="stylesheet/less" scoped>
  @import '../../css/theme.less';
  .show-release-container{
    background-color: #fff;
    width: 80%;
    .title{
      span{
        margin-right: 8px;
        &:nth-child(1), &:nth-child(2){
          font-size: 16px;
          font-weight: 700;
        }
      }
      & > span:nth-child(3){
        margin-left: 8px;
        padding: 2px 10px;
        border: 1px solid @secondColor;
        border-radius: 8px;
        background-color: @secondColor;
        color: #fff;
      }
    }
    .container-right{
      margin: 20px 0;
      min-width: 320px;
      padding: 0 10%;
      .title {
        i{
          color: @secondColor;
          cursor: pointer;
          float: right;
          margin-right: 30px;
          font-size: 20px;
        }
        span{
          display: inline-block;
        }
      }
      & > div{
        margin-bottom: 30px;
      }
      .container-title{
        & > div{
          display: flex;
          justify-content: flex-start;
          margin-bottom: 15px;
          & > div{
            span{
              display: inline-block;
            }
            padding-right: 60px;
            & > span:nth-child(1){
              color: #999;
              margin-right: 8px;
            }
          }
        }
      }
      .container-describe{
        header{
          display: inline;
          padding-right: 20px;
          padding-bottom: 20px;
          border-bottom: 1px solid #999;
        }
        p{
          margin-top: 35px;
        }
      }
    }
    .container-left{
      background-color: @secondColor;
      /*min-width: 300px;*/
      margin-top: -8%;
      color: #fff;
      & > div{
        width: 80%;
        padding: 30px 0;
        margin: 0 auto;
        & > div{
          margin-bottom: 30px;
          & > span{
            &:nth-child(1){
              color: #999;
              font-size: 16px;
            }
            &:nth-child(3){
              font-size: 24px;
              font-weight: 700;
            }
          }
        }
      }
      .container-parameters{
        & > div{
          margin-bottom: 8px;
          & > span:nth-child(1){
            color: #999;
          }
        }
      }
      .container-apply{
        cursor: pointer;
        border-radius: 4px;
        text-align: center;
        padding: 13px 8px;
        background-color: #fff;
        color: @secondColor;
      }
    }
  }
</style>
<template>
  <div class="show-release-container row" >
    <div class="container-left col-md-4">
      <div>
        <div>
          <span>项目预算</span><br>
          <span>{{data.budget}}</span>
        </div>
        <div>
          <span>项目周期</span><br>
          <span>{{data.cycle}}</span>
        </div>
        <slot name="applyBtn"></slot>
        <div class="container-parameters">
          <div>
            <span>申请数</span>
            <span>{{data.applyAmount}}</span>
          </div>
          <div>
            <span>浏览数</span>
            <span>{{data.browse}}</span>
          </div>
        </div>
      </div>
    </div>
    <div class="container-right col-md-8">
      <div class="title">
        <span>项目名称</span><span>{{data.projectName}}</span>
        <span>{{data.status}}</span>
        <slot name="icon"></slot>
      </div>
      <div class="container-title">
        <div>
          <div>
            <span>项目类型</span>
            <span>{{data.firstType}}/{{data.secondType}}</span>
          </div>
          <div>
            <span>公司</span>
            <span>{{data.company}}</span>
          </div>
        </div>
        <div>
          <div>
            <span>发布时间</span>
            <span>{{data.releaseTime}}</span>
          </div>
        </div>
      </div>
      <div class="container-describe">
        <header>项目描述</header>
        <p>{{data.describe}}</p>
      </div>
    </div>
  </div>
</template>
<script>
  export default {
    props: ['data']
  }
</script>
