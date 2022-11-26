<template>
  <div class="page">
    <img class="back_ima" src="https://pic.imgdb.cn/item/6380b89316f2c2beb1f9e183.jpg">
      
    <div class="left">
        <div class="left_top">
            <div class="title"> 网络测量</div>
            <el-form ref="form1" :model="form1" label-width="80px">
          <el-form-item label="主机名">
    <el-input v-model="form1.name" placeholder="输入主机名"></el-input>
  </el-form-item>
  <el-form-item label="另一主机">
    <el-input v-model="form1.name" placeholder="输入另一主机名"></el-input>
  </el-form-item>
        </el-form>
        <el-button type="primary" round>检测</el-button>
        </div>
        <div class="left_bottom">
            <iframe class="iframe"  scrolling="no" src="https://blog.csdn.net/zibingdechengbao/article/details/124867039"></iframe>
        </div>
    </div>
    <div class="right">
        <div class="right_top">
            <div class="title">
                链路带宽
            </div>
        </div>
        <div class="right_bottom">
            <div class="title">
                时延
            </div>
        </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
    data(){
        return{
            form1:{
                name:'',
            }
        }
    },
    methods:{
        
    }
}
</script>

<style scoped>
.right_top{
    height:30%;
}
.right_bottom{
    height:30%;
    margin-top:2%;
}
.right{
    width:45%;
    margin:2.5% 5%;
}
.iframe{
    width:100%;
    height:100%;
}
.left_bottom{
    margin-top:5%;
    height:60vh;
}
.back_ima{
    width:100%;
    height: 100%;
    position: absolute;
    z-index: -1;
    
}
.left_top .el-button{
    width:25%;
    margin:0 37.5%;
    margin-bottom:5%;
} 
.el-form{
    width:80%;

    margin: 5% auto;
}
.left_top{
    border:1px dotted #409EFF;
    border-radius: 15px;
}
.left{
    margin:2.5% 5%;
    width:35%;
    
    
}
.title{
    border-radius: 15px 15px 0 0;
    font-size:30px;
    padding:10px 0;
    background-color:aqua;
    text-align: center;

}
.page{
    width:100%;
   position: relative;
    display: flex;
    flex-wrap: wrap;
    min-height: 100vh;
}

</style>