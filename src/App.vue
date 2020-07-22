<template>
  <div id="app">
    <main v-show="this.data !== null">
      <div id="firstLine">{{month}} 月 {{day}} 日</div>
      <div id="secondLine">{{hour}} : {{minute}} : {{second}}</div>
    </main>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        data: null,
        month: null,
        day: null,
        hour: null,
        minute: null,
        second: null
      }
    },
    methods: {
      getTime() {
        const init = () => {
          getDate()
          getHours()
          getMonth()
          getDay()
          getMinute()
          getSecond()
        }
        const getDate = () => {
          this.data = new Date()
        }
        const getMonth = () => {
          this.month = this.data.getMonth()
        }
        const getDay = () => {
          this.day = this.data.getDay()
        }
        const getHours = () => {
          this.hour = this.data.getHours()
        }
        const getMinute = () => {
          this.minute = this.data.getMinutes()
        }
        const getSecond = () => {
          this.second = this.data.getSeconds()
        }
        init()
      }

    },
    created() {
      setInterval(() => {
        this.getTime()
      }, 1000)
    }
  }
</script>

<style>

  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  main {
    width: 100vw;
    height: 100vh;
    background: black;
    color: white;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    font-size: 3rem;
  }

  #firstLine {
    margin-bottom: 20px;
  }

</style>
