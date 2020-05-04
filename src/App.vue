<template>
  <div id="app" :style="{background: bgColor }">
    <div class="box" v-if="bdayToday">
      <h1><span class="first">Happy</span> <span class="second">birthday</span> <span class="third">Thomas!</span></h1>
    </div>
    <div class="box" v-else>It ain't Thomas's birthday today...</div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      bgColor: 'white',
      bdayToday: false
    }
  },
  mounted() {
    const today = new Date();
    this.bdayToday = today.getDate() === 5 && today.getMonth() === 4;

    if (this.bdayToday) {
      this.$confetti.start();

      this.bgColor = 'rgb(68, 173, 157)';
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@700&display=swap');

* {
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

html, body {
  margin: 0;
  padding: 0;
  font-family: 'Roboto', sans-serif;
  text-shadow: 2px 2px 2px rgba(0, 0, 0, 0.2);
}

.box {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  width: 100%;
}

.first {
  color: #C32C48;
}

.second {
  color: #75B3A7;
}

.third {
  color: #EFBF6A;
}
</style>
