<template>
  <div class="m-menu">
    <dl class="nav" @mouseleave="mouseleave">
      <dt>全部分类</dt>
      <dd v-for="(item, index) in menu" :key="index" @mouseenter="enter">
        <i :class="item.type" />
        {{ item.name }}
        <span class="arrow"></span>
      </dd>
    </dl>
    <div class="detail" v-if="kind" @mouseenter="sover" @mouseleave="sout">
      <template v-for="(item, idx) in curdetail.child">
        <h4 :key="idx">{{ item.title }}</h4>
        <span v-for="v in item.child" :key="v">{{ v }}</span>
      </template>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      kind: "",
      menu: [
        {
          type: "food",
          name: "美食",
          child: [
            {
              title: "美食",
              child: ["代金券", "火锅", "自助餐", "烧烤"]
            }
          ]
        },
        {
          type: "hotel",
          name: "酒店",
          child: [
            {
              title: "酒店星级",
              child: ["经济型", "经济型2", "经济型3", "经济型4"]
            }
          ]
        },
        {
          type: "takeout",
          name: "外卖",
          child: [
            {
              title: "美团外卖",
              child: ["美团外卖", "火锅", "美团外卖2", "烧烤"]
            },
            {
              title: "美团外卖",
              child: ["美团外卖3", "火锅2", "美团外卖2132", "烧烤34"]
            }
          ]
        }
      ]
    };
  },
  computed: {
    curdetail: function() {
      return this.menu.filter(item => item.type === this.kind)[0];
    }
  },
  methods: {
    mouseleave: function() {
      let that = this;
      that._timer = setTimeout(() => {
        that.kind = "";
      }, 250);
    },
    enter: function(e) {
      let that = this;
      setTimeout(() => {
        that.kind = e.target.querySelector("i").className;
        console.log(that.kind);
      }, 250);
    },
    sover: function() {
      clearTimeout(this._timer);
    },
    sout: function() {
      this.kind = "";
    }
  }
};
</script>

<style lang="scss" >
</style>