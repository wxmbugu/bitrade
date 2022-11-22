<template>
  <div class="helplist">
    <img src="../../assets/images/BitcoinBackground.png" class="backimg " alt="">
    <img src="../../assets/images/mobilebackcoin.png"  class=" backimg showmobile " alt=""></img>
    <!-- <div class="route-wrap">
      <router-link to="help">{{$t("header.helpcenter")}}</router-link>
      <span>></span>
      <span>{{cateTitle}}</span>
    </div> -->
    <div class="container">
      <!-- <div class="list">
        <router-link class="item" v-for="(item,index) in list" :key="index" :to="{path:'helpdetail',query:{cate:cate,id:item.id,cateTitle:cateTitle}}">
          <span class="text" >{{item.title}}</span>
          <span class="time">
            {{item.createTime}}
          </span>
        </router-link>
      </div>
      <div class="page">
        <Page :total="total" :pageSize="pageSize" :current="pageNo" @on-change="pageChange"></Page>
      </div> -->
      <Row >
        <Col :xs="24" :sm="24" :md="8" :lg="8">
                                 <h1>{{cateTitle}}</h1>

                           <img v-if="this.cate=='0'" src="../../assets/images/Growcoin.png" class="vert-move imgLogo" style="height:300px;"   alt="">
                          <img v-if="this.cate=='2'" src="../../assets/images/goldcoin.png" class="vert-move imgLogo" style="height:300px;"  alt="">
                          <img v-if="this.cate=='3'" src="../../assets/images/fallcoins.png" class="vert-move imgLogo" style="height:200px;  " alt="">
                          
                          <img v-if="this.cate=='1'" src="../../assets/images/walletcoins.png" class="vert-move imgLogo" style="height:300px; "  alt=""></img>

                        </Col>
                        <Col  :xs="24" :sm="24" :md="16" :lg="16">
                           
      <Collapse  v-model="value2" accordion class="faq">
        <Panel name="1">
            {{$t("faq.question1")}}
            <p slot="content"> {{$t("faq.answer1")}}</p>
        </Panel>
        <Panel name="2">
            {{$t("faq.question2")}}
            <p slot="content"> {{$t("faq.answer2")}}</p>
        </Panel>
        <Panel name="3">
            {{$t("faq.question3")}}
            <p slot="content"> {{$t("faq.answer3")}}</p>
        </Panel>
        <Panel name="4">
            {{$t("faq.question4")}}
            <p slot="content"> {{$t("faq.answer4")}}</p>
        </Panel>
        <Panel name="5">
            {{$t("faq.question5")}}
            <p slot="content"> {{$t("faq.answer5")}}</p>
        </Panel>
        <Panel name="6">
            {{$t("faq.question6")}}
            <p slot="content"> {{$t("faq.answer6")}}</p>
        </Panel>
        <Panel name="7">
            {{$t("faq.question7")}}
            <p slot="content"> {{$t("faq.answer7")}}</p>
        </Panel>
        <Panel name="8">
            {{$t("faq.question8")}}
            <p slot="content"> {{$t("faq.answer8")}}</p>
        </Panel>
         <Panel name="9">
            {{$t("faq.question9")}}
            <p slot="content"> 
              
            {{$t("faq.answer9.part1")}}<br/>
            {{$t("faq.answer9.part2")}}<br/>
            {{$t("faq.answer9.part3")}}<br/>
            {{$t("faq.answer9.part4")}}<br/>
           {{$t("faq.answer9.part5")}}<br/>
              
            </p>
        </Panel>
         <Panel name="10">
            {{$t("faq.question10")}}
            <p slot="content"> {{$t("faq.answer10")}}</p>
        </Panel>
         <Panel name="11">
            {{$t("faq.question11")}}
            <p slot="content"> 
              {{$t("faq.answer11.part1")}}<br/><br/>
              {{$t("faq.answer11.part2")}}<br/><br/>
              {{$t("faq.answer11.part3")}}<br/><br/>
              {{$t("faq.answer11.part4")}}<br/><br/>
              {{$t("faq.answer11.part5")}}<br/><br/>
      
              </p>
        </Panel>
         <Panel name="12">
            {{$t("faq.question12")}}
            <p slot="content"> {{$t("faq.answer12")}}</p>
        </Panel>
        
         <Panel name="13" >
            {{$t("faq.question13")}}
            <p slot="content" style="border-radius:15px;"> {{$t("faq.answer13")}}</p>
        </Panel>
    </Collapse>

                        </Col>
                         
                    </Row>

     
    </div>
  </div>
</template>
<style lang="scss">
.ivu-collapse-item:last-child > .ivu-collapse-content {
  border-radius: 0 0 15px 15px !important;
}
.ivu-collapse > .ivu-collapse-item.ivu-collapse-item-active > .ivu-collapse-header {
  border-bottom: 1px solid #dcdee2;
  height: auto!important;
}
.ivu-collapse > .ivu-collapse-item {
  border-top: 1px solid #dcdee2;
  height: auto !important;
}
.ivu-collapse > .ivu-collapse-item > .ivu-collapse-header{
  height: auto !important;
}
@media only screen and (max-width:768px) {
  .helplist {
  padding: 80px 2% !important;
  height: 1500px;
  }
  .ivu-collapse>.ivu-collapse-item>.ivu-collapse-header{
    height: auto !important;
    line-height: 20px !important;
    padding: 20px 10px !important;
    
  }
  .ivu-collapse>.ivu-collapse-item>.ivu-collapse-content{
    height: auto !important;
    line-height: 20px !important;
    padding: 10px 5% !important;
    
  }
  .imgLogo{
    height: auto;
    width: 200px;
  }
  .helplist .container{
    top:40px !important;
    padding: 20px 5% !important;
  }
  .faq{
    margin-top:30px;
  }
  .backimg{
  height: 900px;
  width:300px;
}
.showmobile{
  display: block;
}

}
.showmobile{
  display: none;
}
.backimg{
 // height: 800px;
 width: 100%;
  height: auto;
}
.faq{
  border-radius: 15px !important;
  background-color:#1e2834 !important;

 opacity: 0.9;
 color: #ffffff;
 //-webkit-box-shadow: -1px 2px 25px 1px rgba(0,0,0,0.92); 
//box-shadow: -1px 2px 25px 1px rgba(0,0,0,0.92);
-webkit-box-shadow: -1px 4px 31px 9px rgba(0,0,0,0.92); 
box-shadow: -1px 4px 31px 9px rgba(0,0,0,0.92);

}
.helplist {
  position: relative;
  width: 100%;
  margin: 0 auto;

 // padding: 80px 20%;
  //background: #FFF;
  background-color: #0b1520;
  color: #ffffff;
  min-height: 1050px;
  height: auto;
  .container {
    position: absolute;
    top: 50px;
     width: 100%;
     padding: 120px 5%;
    > h1 {
      text-align: center;
      margin: 30px 0 20px 0;
    }
    .page {
      text-align:right;
      margin-top: 10px;
      .ivu-page{
        background: transparent!important;
        .ivu-page-prev, .ivu-page-next{
          background-color: transparent!important;
          color: rgb(250, 250, 250);
          border: none;
        }
        .ivu-page-item{
          background-color: transparent!important;
          color:  #ffffff;
          border: none;
        }
      }
    }
  }
}
.ivu-collapse>.ivu-collapse-item>.ivu-collapse-header{
  text-align: left !important;
  color:  #ffffff !important;
  
}
.ivu-collapse-content{
  background-color: #0b1520 !important;
  color:  #ffffff !important;
  text-align: left !important;

}
.list {
  font-size: 16px;
  .item {
    color: #464646;
    display: block;
    line-height: 40px;
    border-bottom: 1px solid #ebebeb;
    cursor: pointer;
    .iconimg {
      width: 14px;
      vertical-align: sub;
      margin-left: 20px;
    }
    .time {
      float: right;
      color: #999;
      font-size: 14px;
    }
    &:hover{
      color: #f0a70a;
    }
  }
}
.route-wrap {
  font-size: 14px;
  a {
    color: #ffec03;
  }
  span {
    color: #ffec03;
  }
}

img.vert-move {
    -webkit-animation: mover 1s infinite  alternate;
    animation: mover 1s infinite  alternate;
}
img.vert-move {
    -webkit-animation: mover 1s infinite  alternate;
    animation: mover 1s infinite  alternate;
}
@-webkit-keyframes mover {
    0% { transform: translateY(0); }
    100% { transform: translateY(+30px); }
}
@keyframes mover {
    0% { transform: translateY(0); }
    100% { transform: translateY(+30px); }
}
</style>
<script>
export default {
  data() {
    return {
      cate: 0,
      pageNo: 1,
      pageSize: 10,
      total: 0,
      list: [],
      value2:'1',
    };
  },
  created() {
    this.$store.commit("navigate", "nav-uc");
    const { cate, cateTitle } = this.$route.query;
    this.cate = cate;
    this.cateTitle = cateTitle;
    this.getData();
  },
  computed: {
    lang() {
      return this.$store.state.lang;
    },
    langPram(){
      this.$store.state.lang
    }
  },
  watch: {
    $route(to, from) {
      const { cate, cateTitle } = to.query;
      this.cate = cate;
      this.cateTitle = cateTitle;
      console.log("catttt",this.cate);
      this.getData();
    }
  },
  methods: {
    pageChange(data) {
      this.pageNo = data;
      this.getData();
    },
    getData() {
      let params = {
        pageNo: this.pageNo,
        pageSize: this.pageSize,
        cate: this.cate,
        lang: this.langPram
      };
      this.$http
        .post(this.host + "/uc/ancillary/more/help/page", params)
        .then(res => {
          if (res.status == 200 && res.body.code == 0) {
            this.list = res.body.data.content;
            this.total = res.body.data.totalElements;
          } else {
            this.$Message.error(res.body.message);
          }
        });
    }
  }
};
</script>


