<template>
  <div class="m-menu">
    <dl
      class="nav"
      @mouseleave="mouseleave"
    >
      <dt>全部分类</dt>
      <dd
        v-for='(item,index) in menu'
        :key="index"
        @mouseenter="enter"
      >
        <i :class="item.type"></i>{{item.name}}<span class="arrow" />
      </dd>
    </dl>
    <div
      class="detail"
      v-if="kind"
      @mouseenter="sover"
      @mouseleave="sout"
    >
      <template v-for="(item,index) in curdetail.child">
        <h4 :key="index">{{item.title}}</h4>
        <span
          v-for="v in item.child"
          :key="v"
        >{{v}}</span>
      </template>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      kind: "", //记录数遍选中那个分类
      menu: [
        {
          type: "food",
          name: "美食",
          child: [
            {
              title: "美食",
              child: ["代金券", "甜点饮品", "火锅", "自助餐", "小吃快餐"]
            }
          ]
        },
        {
          type: "takeout",
          name: "外卖",
          child: [
            {
              title: "外卖",
              child: ["美团外卖"]
            }
          ]
        },
        {
          type: "hotel",
          name: "酒店",
          child: [
            {
              title: "酒店星级",
              child: ["经济型", "舒适/三星", "高档/四星", "豪华/五星"]
            }
          ]
        },
        {
          name: "猫眼电影",
          type: "movie",
          child: [
            {
              title: "热映电影",
              child: [
                "反贪风暴3",
                "碟中谍6：全面瓦解",
                "镰仓物语",
                "李茶的姑妈",
                "黄金兄弟",
                "未择之路",
                "阿尔法：狼伴归途",
                "胖子行动队蚁人2：黄蜂女现身",
                "念念手纪"
              ]
            },
            {
              title: "热门影院",
              child: [
                "耀莱成龙国际影城",
                "保利国际影城",
                "大地影院",
                "万达影城博纳国际影城",
                "CGV影城橙",
                "天嘉禾影城",
                "金逸影城",
                "中影国际影城",
                "新华国际影城"
              ]
            }
          ]
        }
      ]
    };
  },
  computed: {
    curdetail() {
      return this.menu.filter(item => item.type == this.kind)[0];
    }
  },
  methods: {
    mouseleave() {
      let _this = this;
      _this.timer = setTimeout(() => {
        _this.kind = "";
      }, 150);
    },
    enter(e) {
      this.kind = e.target.querySelector("i").className;
    },
    sover() {
      clearTimeout(this.timer);
    },
    sout() {
      this.kind = "";
    }
  }
};
</script>


