<template>
  <div class="main">
    <div class="container">
      <div
        v-for="(block, index) in blocks"
        :key="index"
        class="block"
        :class="{ 'show': block.visible }"
        :style="`background-image: url(${block.src}); `"
        ref="blocks"
      ></div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      blocks: [
        { 
          visible: false,
          src: require('@/assets/images/1.jpeg') 
        },
        { 
          visible: false,
          src: require('@/assets/images/2.jpeg') 
        },
        { 
          visible: false,
          src: require('@/assets/images/3.jpeg') 
        },
        { 
          visible: false,
          src: require('@/assets/images/4.jpeg') 
        },
        { 
          visible: false,
          src: require('@/assets/images/5.jpeg') 
        },
        { 
          visible: false,
          src: require('@/assets/images/6.jpeg') 
        },
        { 
          visible: false,
          src: require('@/assets/images/7.jpeg') 
        },
        { 
          visible: false,
          src: require('@/assets/images/8.jpeg') 
        },
        { 
          visible: false,
          src: require('@/assets/images/9.jpeg') 
        },
        { 
          visible: false,
          src: require('@/assets/images/1.jpeg') 
        },
        { 
          visible: false,
          src: require('@/assets/images/2.jpeg') 
        },
        { 
          visible: false,
          src: require('@/assets/images/3.jpeg') 
        }
      ],
    };
  },
  mounted() {
    window.addEventListener("scroll", this.checkVisibility);
    this.checkVisibility();
  },
  beforeDestroy() {
    window.removeEventListener("scroll", this.checkVisibility);
  },
  methods: {
    checkVisibility() {
      const windowHeight = window.innerHeight;
      const scrollTop = window.scrollY || document.documentElement.scrollTop;

      this.blocks.forEach((block, index) => {
        const blockTop = this.$refs.blocks[index].offsetTop;
        block.visible = blockTop < scrollTop + windowHeight - 200;
      });
    },
  },
};
</script>

<style lang="scss">
.main{
  margin-top: 100px;
  padding-top: 40px;
  background-color: #afe2b561;
  .container {
    width: 1200px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    overflow: hidden;
    .block {
      height: 400px;
      margin: 10px;
      opacity: 0;
      transition: opacity 1s linear;
      background-position: center;
      background-size: 210px;
      background-repeat: no-repeat;
      box-shadow: 0 0 10px 0 #c1c1c1;
      background-color: white;

      &.show {
        opacity: 1;
      }
    }
  }
}
</style>