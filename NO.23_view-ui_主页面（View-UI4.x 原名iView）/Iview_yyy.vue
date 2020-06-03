<template>
    <div style="background:#eeeeee;font-size:20px;">

        <!-- -------------头部------------- -->
        <Row type="flex" justify="center" style="background:#409eff; font-size:15px; padding: 8px 0 10px 0;"> 
            <Col span="15">
                <h1 style="color:#fff">{{ pj_name }}</h1>
            </Col>
        </Row>

        <!-- -------------简介------------- -->
        <Row type="flex" justify="center" style="padding: 40px 0 40px 0;">
            <Col span="15">
                <br>
                <h1 style="font-size:50px" >Hello,{{ welcome }},...</h1>
                <p>This is a template for a simple marketing or informational website. It includes a large callout called a jumbotron and three supporting pieces of content. Use it as a starting point to create something more unique.</p>
                <br>
                <Button size='large' type="primary">Learn more >></Button>

            </Col>
        </Row>

        <!-- -------------主体------------- -->
        <Row type="flex" justify="center" style="padding: 0px 0 30px 0;">
            <!-- <Col span="15" style="background:#409eff;"> -->
            <Col span="15" >
                <Card class="Card" v-for="heading in headings" :key=heading>
                    <br>
                    <h2>{{heading}}</h2>
                    <br>
                    <p style="font-size:16px;">Donec id elit non mi porta gravida at eget metus. Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh.</p>
                    <Button size='small' >View details >></Button>
                    <br>
                    <br>
                </Card>
            </Col>
        </Row>

        <!-- -------------结尾------------- -->
        <Row type="flex" justify="center" style="padding: 20px 0 20px 0;">
        <!-- <Col span="15" style="background:#409eff;"> -->
            <Col span="15" >
                <div style="background-color:#bbbbbb;height:2px;"></div>
                <br>
                <p>© 2020 Company, Inc.</p>
            </Col>
        </Row>

    </div>
</template>

<script>
    export default {
        data () {
            return {
                headings:['1Heading','2Heading','3Heading', '4Heading','5Heading','6Heading'],
                welcome: 'Vue.js,Element-UI',
                pj_name: 'Project Name'
            }
        },
        methods: {
  
            },

    }
</script>

<style lang="less" scoped>

.Card{ // 原生css
    background:#fbfbfb;
    width: 305px;
    // height: 300px;
    display: inline-block;
    margin: 0.3em;
    border-radius:20px;
    // justify-content: center; // 这样会使得Card里面的元素居中
    box-shadow: 5px 5px 5px 5px #cccccc; 
}

.Form{
    padding: 5%;
}
</style>
