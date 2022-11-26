<template>
  <div class="page">
    <img class="back_ima" src="https://pic.imgdb.cn/item/6380b89316f2c2beb1f9e183.jpg">
    <el-tabs v-model="activeName" type="card" @tab-click="handleClick">
    <el-tab-pane  name="first">
      <span slot="label" :class="[tab_index==0?'tab_content1':'tab_content']"> 导入拓扑</span>
     <div class="main">
      <div class="left_content">
        <el-upload
    class="upload-demo"
  drag
  action="https://jsonplaceholder.typicode.com/posts/"
  multiple>
  <i class="el-icon-upload"></i>
  <div class="el-upload__text">将文件拖到此处，或<em>点击上传</em></div>
  
</el-upload>
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
    <el-tab-pane label="主机增删" name="second">
      <span slot="label" :class="[tab_index==1?'tab_content1':'tab_content']"> 主机增删</span>
      <div class="main">
      <div class="left_content1">
        <div class="title">主机增删</div>
        <el-form ref="form1" :model="form1" label-width="80px">
          <el-form-item label="操作类型">
    <el-select v-model="form1.type" placeholder="请选择操作类型">
      <el-option label="增加主机" value="add"></el-option>
      <el-option label="删除主机" value="del"></el-option>
    </el-select>
  </el-form-item>
          <el-form-item label="主机名">
    <el-input v-model="form1.name"></el-input>
  </el-form-item>
  <el-form-item v-if="form1.type=='add'" label="IP地址">
    <el-input v-model="form1.ip"></el-input>
  </el-form-item>
  <el-form-item  v-if="form1.type=='add'" label="连交换机">
    <el-input v-model="form1.toname"></el-input>
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
    <el-tab-pane label="交换机增删" name="third">
      <span slot="label" :class="[tab_index==2?'tab_content1':'tab_content']"> 交换机增删</span>
      <div class="main">
      <div class="left_content1">
        <div class="title">交换机增删</div>
        <el-form ref="form2" :model="form2" label-width="80px">
          <el-form-item label="操作类型">
    <el-select v-model="form2.type" placeholder="请选择操作类型">
      <el-option label="增加交换机" value="add"></el-option>
      <el-option label="删除交换机" value="del"></el-option>
    </el-select>
  </el-form-item>
          <el-form-item label="主机名">
    <el-input v-model="form2.name"></el-input>
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
    <el-tab-pane label="链路增删" name="fourth">
      <span slot="label" :class="[tab_index==3?'tab_content1':'tab_content']"> 链路增删</span>
      <div class="main">
      <div class="left_content1">
        <div class="title">链路增删</div>
        <el-form ref="form3" :model="form3" label-width="80px">
          <el-form-item label="操作类型">
    <el-select v-model="form3.type" placeholder="请选择操作类型">
      <el-option label="增加链路" value="add"></el-option>
      <el-option label="删除链路" value="del"></el-option>
    </el-select>
  </el-form-item>
          <el-form-item label="主机名">
    <el-input v-model="form3.name"></el-input>
  </el-form-item>
  <el-form-item label="另一主机名">
    <el-input v-model="form3.toname"></el-input>
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
  </el-tabs>
   
  </div>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  name: 'Dashboard',
  computed: {
    ...mapGetters([
      'name'
    ])
  },
  data(){
    return {
      tab_index:0,
      form1:{
        type:'add',
        name:'',
        toname:'',
        ip:''
      },
      form2:{
        type:'add',
        name:'',
       
      },
      form3:{
        type:'add',
        name:'',
       toname:''
      },
        activeName: 'first'
      };
  },
  methods:{
    handleClick(e){
      this.tab_index=e.index
      console.log(this.tab_index)
    }
  }
}
</script>


<style lang="scss" scoped>

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
.page{
  width:100%;
   position: relative;
    display: flex;
    flex-wrap: wrap;
    min-height: 100vh;
}
.back_ima{
  width:100%;
  height:100%;
  position:absolute;
  z-index:-1;
}
 .el-input{
  width:70%;
}
.title{
  text-align: center;
  font-size: 25px;
  background-color: #2BD5D5;
  border-radius:15px 15px 0 0 ;
  padding:10px 0;
  color:rgb(0, 0, 0);
}
.upload_btns{
  margin:5% auto;;
  width:80%;
}
.left_content1{
  width:30%;
  border:1px dashed #409EFF;
  
  border-radius: 15px;
}
.el-form{
  width:90%;
  margin:5%;
}
.el-button{
  width:30%;
  margin:0 10%;
}
.el-upload el-upload--text{
  width:80%;
  margin:0 auto;
  
}
.upload-demo{
  width:100%;
  text-align: center;
}
.main{
  display: flex;
  margin-top:5%;
}

.left_content{
width:30%;
margin-top:7%;
}
.view{
  width:60%;
  margin:0 5%;
}

.iframe{
  width:100%;
  
  height:60vh;
}
.dashboard {
  &-container {
    margin: 30px;
  }
  &-text {
    font-size: 30px;
    line-height: 46px;
  }
}
</style>
