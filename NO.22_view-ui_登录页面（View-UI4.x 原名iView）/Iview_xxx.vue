<template>
    <div style="background:#eeeeee;">
        <!-- 头部空位 -->
        <Row type="flex" justify="center">
            <Col span="8" style="height:150px;"></Col>
        </Row>

        <!-- 主体部分 -->
        <Row type="flex" justify="center">
            <Col span="8" style="height:600px;">
                <Layout>
                    <Content style="display:flex;justify-content:center;background:#eeeeee">
                        <Card class="Card">
                            <br>
                            <h1 style="text-align: center;font-size:32px;">欢迎登陆</h1>
                            <br>
                            <div style="background-color:#dddddd;height:2px;"></div>
                            <br>
                            <Form class="Form" ref="formValidate" :model="formValidate" :rules="ruleValidate" :label-width="80">
                                <FormItem label="用户名" prop="name" >
                                    <Input v-model="formValidate.name" placeholder="请输入用户名"></Input>
                                </FormItem>
                                <FormItem label="密码" prop="password">
                                    <Input type="password" v-model="formValidate.password" placeholder="请输入密码"></Input>
                                </FormItem>

                                <FormItem prop="g">
                                    <RadioGroup v-model="formValidate.g">
                                        <Radio label='a'>仅前端</Radio>
                                        <Radio label='b'>发送给后端</Radio>
                                    </RadioGroup>
                                </FormItem>

                                <FormItem v-show="formValidate.g==='b'" label="IP地址" prop="ip">
                                    <Input v-model="formValidate.ip" ></Input>
                                </FormItem>
                                <FormItem>
                                    <Button type="primary" @click="handleSubmit('formValidate')">Submit</Button>
                                    <Button @click="handleReset('formValidate')" style="margin-left: 8px">Reset</Button>
                                </FormItem>
                            </Form>
                        </Card>
                    </Content>
                </Layout>
            </Col>
        </Row>
    </div>
</template>

<script>
    export default {
        data () {
            return {
                formValidate: {
                    name: '',
                    password: '',
                    g: 'a',
                    ip: 'http://192.168.101.55/'
                },
                ruleValidate: {
                    name: [
                        { required: true, message: '用户名不能为空', trigger: 'blur' }
                    ],
                    password: [
                        { required: true, message: '密码不能为空', trigger: 'blur' },
                    ],
                    ip: [
                        { required: true, message: '后端IP地址不能为空', trigger: 'blur' },
                    ],
                    g: [
                        { required: true, message: '', trigger: 'change' }
                    ],
                }
            }
        },
        methods: {
            handleSubmit (name) {
                this.$refs[name].validate((valid) => {
                    if (valid) {
                        this.$Message.success(`用户名：${this.formValidate.name}，密码：${this.formValidate.password}`);
                    } else {
                        this.$Message.error('格式错误，请检查！');
                    }
                })
            },
            handleReset (name) {
                this.$refs[name].resetFields();
            }
        }
    }
</script>

<style lang="less" scoped>
.Card{ // 原生css
    border-radius:30px;
    width: 370px;
    // justify-content: center; // 这样会使得Card里面的元素居中
    box-shadow: 5px 5px 5px 5px #cccccc; 
}
.Form{
    padding: 5%;
}
</style>
