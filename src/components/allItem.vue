<template>
    <li class="allItemWrap" @click='fn1'>
        <div class="pic">
           <slot name="pic"></slot> 
        </div>
        <div class="text">
            <slot name="txt"></slot>
            <div class="bot">
                <label class="time">{{ time }}</label>
                <label class="view">{{ view }}</label>
            </div>
        </div>
    </li>
</template>

<script>
export default {
  components: {},
  props: ["time", "view", "id"],
  methods: {
    fn1: function() {
      this.$router.push({
        name: "Commentdetail",
        params: {
          id: this.id
        }
      });
    }
  }
};
</script>

<style>
.allItemWrap {
  overflow: hidden;
  background: #fff;
  padding: 0.15rem;
  position: relative;
  border-bottom: 1px solid #efefef;
  list-style: none;
}

.allItemWrap .pic {
  float: left;
  width: 0.9rem;
  height: 0.64rem;
}

.allItemWrap .pic img {
  width: 100%;
  height: 100%;
  vertical-align: top;
  float: left;
}

.allItemWrap .text {
  margin-left: 1rem;
  min-height: 0.64rem;
}

.allItemWrap .bot {
  padding-top: 0.1rem;
}

.allItemWrap h2 {
  min-height: 0.4rem;
  color: #404040;
  font-size: 0.14rem;
  overflow: hidden;
  text-overflow: ellipsis;
  line-height: 0.2rem;
}

.allItemWrap .text label {
  margin-right: 0.05rem;
  height: 0.12rem;
  line-height: 0.12rem;
  float: left;
  font-size: 0.11rem;
  color: #909090;
  padding-left: 0.22rem;
  margin-right: 0.15rem;
}

.allItemWrap .text .time {
  background-image: url(../assets/images/time.png);
  background-repeat: no-repeat;
  background-position: left center;
  background-size: contain;
}

.allItemWrap .text .view {
  background-image: url(../assets/images/view.png);
  background-repeat: no-repeat;
  background-position: left center;
  background-size: contain;
}
</style>
