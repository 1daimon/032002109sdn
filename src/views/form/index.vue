<template>
<div class="page">
  <img class="back_ima" src="https://pic.imgdb.cn/item/6380b89316f2c2beb1f9e183.jpg">
  <el-tabs type="card" style="background:none;border:0" @tab-click="handleClick">
  <el-tab-pane >
    <span slot="label" :class="[tab_index==0?'tab_content1':'tab_content']"> 流表查询删除</span>
    <div class="main">
     
      <div class="left_content1">
        <div class="title">流表查询删除</div>
        <el-form ref="form1" :model="form1" label-width="80px">
          
          <el-form-item label="交换机名">
    <el-input v-model="form1.name"></el-input>
  </el-form-item>
  <el-form-item  label="流表">
    <el-card class="box-card">
  <div v-for="index in 10" :key="o" :class="[index%2==1?'item1':'item']">
    {{'列表内容日日日日日日日日日日日日日日日日日日日' + index }}
  </div>
</el-card>
  </el-form-item>
 

</el-form>
<div class="upload_btns">
  <el-button type="primary" round>查看</el-button>
<el-button type="success" round>删除</el-button>
</div>
      </div>
      <div class="view">
        <div class="title">拓扑视图</div>
  <iframe class="iframe"  scrolling="no" src="https://blog.csdn.net/zibingdechengbao/article/details/124867039"></iframe>
      </div>
     </div>
  </el-tab-pane>
  <el-tab-pane >
    <span slot="label" :class="[tab_index==1?'tab_content1':'tab_content']"> 流表新增</span>
    <div class="main">
     
      <div class="left_content1">
        <div class="title">流表新增</div>
        <el-form ref="form1" :model="form1" label-width="80px">
  <el-form-item  label="流表参数">
    <el-card class="box-card">
    
    jjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjj
    jjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjj
 
</el-card>
  </el-form-item>
</el-form>
<div class="upload_btns">
  <el-button type="primary" round>确定</el-button>
<el-button type="success" round>取消</el-button>
</div>
      </div>
      <div class="view">
        <div class="title">拓扑视图</div>
  <iframe class="iframe"  scrolling="no" src="https://blog.csdn.net/zibingdechengbao/article/details/124867039"></iframe>
      </div>
     </div>
  </el-tab-pane>
  <el-tab-pane >
    <span slot="label" :class="[tab_index==2?'tab_content1':'tab_content']"> 文件导入流表</span>
   <div class="main">
   
    <div class="left_content1">
      <div class="title">文件导入流表 </div>
      <el-upload
  class="upload-demo"
  drag
  action="https://jsonplaceholder.typicode.com/posts/"
  multiple>
  <i class="el-icon-upload"></i>
  <div class="el-upload__text">将文件拖到此处，或<em>点击上传</em></div>
  <div class="el-upload__tip" slot="tip">只能上传py文件</div>
</el-upload>
    </div>
    <div class="view">
      <div class="title">拓扑视图</div>
  <iframe class="iframe"  scrolling="no" src="https://blog.csdn.net/zibingdechengbao/article/details/124867039"></iframe>
      </div>
   </div>

  </el-tab-pane>
</el-tabs>
</div>
</template>

<script>
export default {
  data() {
    return {
      tab_index:0,
      form1: {
        name: '',
        quid_form:''
      }
    }
  },
  methods: {
    onSubmit() {
      this.$message('submit!')
    },
    onCancel() {
      this.$message({
        message: 'cancel!',
        type: 'warning'
      })
    },
    handleClick(e){
      this.tab_index=e.index
    }

  }
}
</script>

<style scoped>
.tab_content{
  color:white;
}
.tab_content:hover{
  color:#409EFF;
}
.tab_content1{
  color:#409EFF;
}
.el-tabs{
  
  width:100%;
}
.back_ima{
  width:100%;
    height: 100%;
    position: absolute;
    z-index: -1;
}
 .upload-demo{
  margin-top:20%;
  text-align: center;
  background:#E6E6E6;
  padding:10px 0;
 }
.insert_luid{
  height:100%;
  overflow: auto;
  width:100%;
}
  .item1 {
    padding: 18px 0;
    font-size: 14px;
    width:100%;
    background-color: #D5D5D5;
  }
  .el-card__body{
    width:100%;
    height:100%;
  }
  .item{
    width:100%;
    padding: 18px 0;
    font-size: 14px;
  }

  .box-card {
    height:40vh;
    width: 90%;
    overflow:auto
  }
.left_content1{
    width:30%;
    margin:0 2.5%;
    border:1px dashed #409EFF;
  
  border-radius: 15px;
}

.title{
  text-align: center;
  font-size: 25px;
  background-color: #2BD5D5;
  border-radius:15px 15px 0 0 ;
  padding:10px 0;
  color:white;
}
.el-form{
  width:80%;
  margin:5% auto;
}
.iframe{
  width:100%;
  height:100%;
}
.page{
  width:100%;
   position: relative;
    display: flex;
    flex-wrap: wrap;
    min-height: 100vh;
}
.el-button{
  width:30%;
  margin:0 10%;
}
.upload_btns{
  margin:5% auto;;
  width:80%;
}
.view{
  margin:0 2.5%;
  width:60%;
  height:70vh;
}

.line{
  text-align: center;
}
.main{
  display:flex;
  margin-top:5%;
  margin-bottom: 3%;
}
</style>

