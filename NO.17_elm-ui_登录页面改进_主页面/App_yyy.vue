<template>
  <div id="app">
    <el-row  class="row-header" type="flex" justify="center" >
      <el-col :span="15" >
        <h2 class='header-h2'>{{ pj_name }}</h2>
      </el-col>
    </el-row>

    
    <el-row style="height:280px;background:#eeeeee" type="flex" justify="center" >
      <el-col :span="15">
        <br>
        <h1 style="font-size:50px" >Hello,{{ welcome }},...</h1>
        <p>This is a template for a simple marketing or informational website. It includes a large callout called a jumbotron and three supporting pieces of content. Use it as a starting point to create something more unique.</p>
        <el-button type="primary">Learn more >></el-button>
        <br>
      </el-col>
    </el-row>


    <el-row style="background:#eeeeee" type="flex" justify="center" >
      <el-col :span="15">
        <el-card shadow="never" v-for="heading in headings" :key=heading>
          <h2>{{heading}}</h2>
          <p>Donec id elit non mi porta gravida at eget metus. Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh.</p>
          <el-button size="small">View details >></el-button>
        </el-card>
      </el-col>
    </el-row>
         

    <el-row style="background:#eeeeee" type="flex" justify="center" >
      <el-col :span="15" >
        <el-divider></el-divider>
        <p>© 2020 Company, Inc.</p>
      </el-col>
    </el-row>

  </div>
</template>

<script>
import Vue from 'vue';
    export default {
        data() 
        {
            return {
                headings:['1Heading','2Heading','3Heading', '4Heading','5Heading','6Heading'],
                welcome: 'Vue.js,Element-UI',
                pj_name: 'Project Name'
            };
        },
        methods: {
            submitForm(formName) 
            {
                this.$refs[formName].validate((valid) => 
                    {
                        if (valid) 
                        {
                            alert('Name:'+this.nameValidateForm.name+';Password:'+this.nameValidateForm.password);
                            // console.log(this.nameValidateForm.name);
                        } else 
                        {
                            console.log('error submit!!');
                            return false;
                        }
                    }
                );
            },
            resetForm(formName) {
                this.$refs[formName].resetFields();
            }
        }
    }
</script>

<style>
  .el-card{
    background:#fbfbfb;
    width: 300px;
    display: inline-block;
    margin: 0.3em;
    border-radius:20px;
  }
  .grid-content {
    /* background: rgb(14, 214, 131); */
    border-radius: 4px;
    min-height: 80px;
  }

  .text {
    font-size: 14px;
  }

  .item {
    padding: 18px 0;
  }
  .header-h2{
 color:#d1d1d1 ;

  }
  .header-h2:hover{
 color:#fff ;

  }
.row-header{
  background:#409eff;
}


</style>
