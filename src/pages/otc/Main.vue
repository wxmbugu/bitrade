<template>
<div>
  <div v-if="!isMobile()" class="content-wraps">
    <div class="containers" id="List">
      <div class="fiat">
        <div class="to_business">
          <h3>{{$t('otc.title')}}</h3>
          <span>{{$t('otc.desc')}}</span>
          <a href="javascript:void(0)" @click="goBusiness">{{$t('otc.buttontxt')}}</a>
          <!-- <router-link to="/identbusiness">成为商家</router-link> -->
        </div>
      </div>
      <div class="content">
        <Menu ref="navMenu" mode="horizontal" width="auto" :active-name="activeMenuName" @on-select="menuSelected" class='tradelist'>
          <MenuGroup>
            <template v-for="(coin,index) in coins">
              <MenuItem :name="'coin-'+index"> {{coin.unit}}
              </MenuItem>
            </template>
          </MenuGroup>
        </Menu>
        <router-view></router-view>
      </div>
      <div class="advantage">
        <ul>
          <li>
            <div class="image"><img src="../../assets/images/price.png" alt=""></div>
            <div class="title">{{$t('otc.title1')}}</div>
            <div class="content1">{{$t('otc.desc1')}}</div>
          </li>
          <li>
            <div class="image"><img src="../../assets/images/poundage.png" alt=""></div>
            <div class="title">{{$t('otc.title2')}}</div>
            <div class="content1">{{$t('otc.desc2')}}</div>
            <li>
              <div class="image"><img src="../../assets/images/instant.png" alt=""></div>
              <div class="title">{{$t('otc.title3')}}</div>
              <div class="content1">{{$t('otc.desc3')}}</div>
            </li>
            <li>
              <div class="image"><img src="../../assets/images/platedanbao.png" alt=""></div>
              <div class="title">{{$t('otc.title4')}}</div>
              <div class="content1">{{$t('otc.desc4')}}</div>
            </li>
        </ul>
      </div>
    </div>
  </div>
  <div v-if="isMobile()" class="content-wraps-mobile">
    <div class="containers" id="List">
      <div class="fiat">
        <div class="to_business">
          <h3>{{$t('otc.title')}}</h3>
          <span>{{$t('otc.desc')}}</span>
          <a href="javascript:void(0)" @click="goBusiness">{{$t('otc.buttontxt')}}</a>
          <!-- <router-link to="/identbusiness">成为商家</router-link> -->
        </div>
      </div>
      <div class="content">
        <Menu ref="navMenu" mode="horizontal" width="auto" :active-name="activeMenuName" @on-select="menuSelected" class='tradelist'>
          <MenuGroup>
            <template v-for="(coin,index) in coins">
              <MenuItem :name="'coin-'+index"> {{coin.unit}}
              </MenuItem>
            </template>
          </MenuGroup>
        </Menu>
        <router-view></router-view>
      </div>
      <div class="advantage-mobile">
        <ul>
          <li>
            <div class="image"><img src="../../assets/images/price.png" alt=""></div>
            <div class="title">{{$t('otc.title1')}}</div>
            <div class="content1">{{$t('otc.desc1')}}</div>
          </li>
          <li>
            <div class="image"><img src="../../assets/images/poundage.png" alt=""></div>
            <div class="title">{{$t('otc.title2')}}</div>
            <div class="content1">{{$t('otc.desc2')}}</div>
            <li>
              <div class="image"><img src="../../assets/images/instant.png" alt=""></div>
              <div class="title">{{$t('otc.title3')}}</div>
              <div class="content1">{{$t('otc.desc3')}}</div>
            </li>
            <li>
              <div class="image"><img src="../../assets/images/platedanbao.png" alt=""></div>
              <div class="title">{{$t('otc.title4')}}</div>
              <div class="content1">{{$t('otc.desc4')}}</div>
            </li>
        </ul>
      </div>
    </div>
  </div>
</div>
</template>

<style scoped lang="scss">

.content-wraps {
  padding: 0 12%;
  // background-color: #fff;
  padding-top: 60px;
  .containers {
    width: 100%;
    margin: 20px 0;
    .fiat {
      border-radius: 5px;
      height: 250px;
      background: url("../../assets/images/otc_bg.jpg") no-repeat center center;
      background-size: 100%;
      display: flex; //flex布局
      justify-content: center; //使子项目水平居中
      align-items: center; //使子项目垂直居中
      .to_business {
        color: #fff;
        text-align: center;
        h3 {
          font-size: 46px;
          letter-spacing: 20px;
        }
        span {
          font-size: 20px;
          letter-spacing: 10px;
          display: block;
        }
        a {
          width: 220px;
          height: 45px;
          display: inline-block;
          background: #ffa400;
          border-radius: 5px;
          font-size: 20px;
          line-height: 45px;
          color: #000;
          margin-top: 20px;
        }
      }
      .to_business-mobile {
        color: #fff;
        text-align: center;
        h3 {
          font-size: 25px;
          letter-spacing: 10px;
        }
        span {
          font-size: 12px;
          letter-spacing: 5px;
          display: block;
        }
        a {
          width: 220px;
          height: 45px;
          display: inline-block;
          background: #ffa400;
          border-radius: 5px;
          font-size: 20px;
          line-height: 45px;
          color: #000;
          margin-top: 20px;
        }
      }
    }
    
    .content {
      width: 100%;
      margin: 20px auto;
      background-color: #192330;
      border-radius: 4px;
    }
    .advantage {
      background-color: #192330;
      border-radius: 4px;
      ul {
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 30px;
        li {
          width: 25%;
          list-style-type: none;
          min-height: 190px;
          div {
            text-align: center;
          }
          div.image {
            width: 50px;
            height: 50px;
            margin: 20px auto;
            img {
              width: 80%;
              // height: 80%;
              vertical-align: middle;
            }
          }
          div.title {
            line-height: 30px;
            font-size: 16px;
            color: #fff;
          }
          div.content1 {
            padding: 20px 40px;
            line-height: 20px;
            font-size: 12px;
            color: #999;
            min-height: 130px;
          }
        }
      }
    }
    .advantage-mobile {
      background-color: #192330;
      border-radius: 4px;
      ul {
        display: block;
        justify-content: center;
        align-items: center;
        padding: 30px;
        li {
          width: 100%;
          list-style-type: none;
          min-height: 190px;
          div {
            text-align: center;
          }
          div.image {
            width: 50px;
            height: 50px;
            margin: 20px auto;
            img {
              width: 80%;
              // height: 80%;
              vertical-align: middle;
            }
          }
          div.title {
            line-height: 30px;
            font-size: 16px;
            color: #fff;
          }
          div.content1 {
            padding: 20px 40px;
            line-height: 20px;
            font-size: 12px;
            color: #999;
          }
        }
      }
    }
  }
}
.content-wraps-mobile {
  padding: 0 2%;
  // background-color: #fff;
  padding-top: 60px;
  .containers {
    width: 100%;
    margin: 20px 0;
    .fiat {
      border-radius: 5px;
      height: 250px;
      background: url("../../assets/images/otc_bg.jpg") no-repeat center center;
      //background-size: 100%;
      display: flex; //flex布局
      justify-content: center; //使子项目水平居中
      align-items: center; //使子项目垂直居中
      .to_business {
        color: #fff;
        text-align: center;
        h3 {
          font-size: 25px;
          letter-spacing: 10px;
        }
        span {
          font-size: 12px;
          letter-spacing: 5px;
          display: block;
        }
        a {
          width: 220px;
          height: 45px;
          display: inline-block;
          background: #ffa400;
          border-radius: 5px;
          font-size: 20px;
          line-height: 45px;
          color: #000;
          margin-top: 20px;
        }
      }
      .to_business-mobile {
        color: #fff;
        text-align: center;
        h3 {
          font-size: 25px;
          letter-spacing: 10px;
        }
        span {
          font-size: 12px;
          letter-spacing: 5px;
          display: block;
        }
        a {
          width: 220px;
          height: 45px;
          display: inline-block;
          background: #ffa400;
          border-radius: 5px;
          font-size: 20px;
          line-height: 45px;
          color: #000;
          margin-top: 20px;
        }
      }
    }
    
    .content {
      width: 100%;
      margin: 20px auto;
      background-color: #192330;
      border-radius: 4px;
    }
    .advantage {
      background-color: #192330;
      border-radius: 4px;
      ul {
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 30px;
        li {
          width: 25%;
          list-style-type: none;
          min-height: 190px;
          div {
            text-align: center;
          }
          div.image {
            width: 50px;
            height: 50px;
            margin: 20px auto;
            img {
              width: 80%;
              // height: 80%;
              vertical-align: middle;
            }
          }
          div.title {
            line-height: 30px;
            font-size: 16px;
            color: #fff;
          }
          div.content1 {
            padding: 20px 40px;
            line-height: 20px;
            font-size: 12px;
            color: #999;
          }
        }
      }
    }
    .advantage-mobile {
      background-color: #192330;
      border-radius: 4px;
      ul {
        display: block;
        justify-content: center;
        align-items: center;
        padding: 30px;
        li {
          width: 100%;
          list-style-type: none;
          min-height: 190px;
          div {
            text-align: center;
          }
          div.image {
            width: 50px;
            height: 50px;
            margin: 20px auto;
            img {
              width: 80%;
              // height: 80%;
              vertical-align: middle;
            }
          }
          div.title {
            line-height: 30px;
            font-size: 16px;
            color: #fff;
          }
          div.content1 {
            padding: 20px 40px;
            line-height: 20px;
            font-size: 12px;
            color: #999;
          }
        }
      }
    }
  }
}
</style>
<style lang="scss">
.content-wraps {
  .containers {
    .content {
      ul.tradelist.ivu-menu.ivu-menu-light.ivu-menu-horizontal {
        background-color: #192330;
        border-radius: 4px;
        &:after {
          background: none;
        }
        .ivu-menu-item-group {
          li.ivu-menu-item {
            border: none;
            &:hover {
              color: #f0ac19;
              border-bottom: 0;
            }
          }
          li.ivu-menu-item.ivu-menu-item-active.ivu-menu-item-selected {
            color: #f0ac19;
            border-bottom: none;
          }
        }
      }
      .nav-right.tradeCenter .list-content .ivu-tabs .ivu-tabs-tabpane {
        .ivu-table-wrapper {
          .ivu-spin.ivu-spin-large.ivu-spin-fix {
            border-color: #fff;
          }
        }
      }
    }
  }
}

</style>
<script>
export default {
  data() {
    return {
      coins: [],
      activeMenuName: "coin-1"
    };
  },
  computed: {
    isLogin: function() {
      return this.$store.getters.isLogin;
    }
  },
  watch:{
    $route(to, from) {
      this.activeMenu();
    }
  },
  methods: {
   isMobile() {
　　let flag = navigator.userAgent.match(/(phone|pad|pod|iPhone|iPod|ios|iPad|Android|Mobile|BlackBerry|IEMobile|MQQBrowser|JUC|Fennec|wOSBrowser|BrowserNG|WebOS|Symbian|Windows Phone)/i)
    　　return flag;
    },
    init() {
      this.$store.commit("navigate", "nav-otc");
      this.$http.post(this.host + this.api.otc.coin).then(response => {
        if (response.body.code == 0) {
          this.coins = response.body.data;
          this.activeMenu();
          this.$nextTick(function() {
            this.$refs.navMenu.updateActiveName();
          });
        }
      });
    },
    goBusiness() {
      if (this.isLogin) {
        this.$router.push({
          path: "/identbusiness"
        });
      } else {
        this.$Message.warning("Please log in first");
      }
    },
    menuSelected(menuName) {
      if (menuName.startsWith("coin")) {
        var coin = this.coins[menuName.split("-")[1]];
        this.$router.push({path: "/otc/trade/" + coin.unit, query: {unit: coin.unit}});
      } else {
        this.$router.push("/otc/" + menuName);
      }
    },
    activeMenu() {
      let coin = this.$route.params[0] || "USDT";
      coin = coin.toUpperCase();
      let index=0;
      this.coins.forEach((v,i)=>{
        if(v.unit===coin){
          index=i;
        }
      })
      this.activeMenuName = `coin-${index}`;
      this.$nextTick(function() {
        this.$refs.navMenu.updateActiveName();
      });
    }
  },
  created: function() {
    this.init();
    // this.activeMenuName = "coin-1";
    // this.$nextTick(function() {
    //   this.$refs.navMenu.updateActiveName();
    // });
  }
};
</script>
