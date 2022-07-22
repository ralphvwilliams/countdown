<template>
  <!-- <div class="img">
    <img src="@/assets/pattern-hills.svg" alt="" />
  </div>
  <div class="second-img">
    <img src="@/assets/bg-stars.svg" alt="" />
  </div>

  <div class="head">
    <h3>WE'RE LAUNCHING SOON</h3>
  </div>
  <div class="wrapper">
    <div class="time-wrapper">
      <div class="time" v-for="prop in Object.entries(time)">
        <p class="value">{{ prop[1] }}</p>
        <p class="key">{{ prop[0] }}</p>
      </div>
    </div>
  </div> -->

  <div class="background">
    <figure class="bgimage-1">
      <img src="@/assets/bg-stars.svg" alt="" />
    </figure>
    <figure class="bgimage-2">
      <img src="@/assets/pattern-hills.svg" alt="" />
    </figure>
    <h1 class="header-text">We’re launching soon</h1>
    <div class="containers">
      <div class="container">
        <div class="card">
          <div class="card-top"></div>
          <!-- <hr /> -->
          <div class="card-bottom">
            <p class="time">{{ time.days }}</p>
          </div>
        </div>
        <p class="time-text">DAYS</p>
      </div>
      <div class="container">
        <div class="card">
          <div class="card-top"></div>
          <!-- <hr /> -->
          <div class="card-bottom">
            <p class="time">{{ time.hours }}</p>
          </div>
        </div>
        <p class="time-text">HOURS</p>
      </div>
      <div class="container">
        <div class="card">
          <div class="card-top"></div>
          <!-- <hr /> -->
          <div class="card-bottom">
            <p class="time">{{ time.minutes }}</p>
          </div>
        </div>
        <p class="time-text">MINUTES</p>
      </div>
      <div class="container">
        <div class="card">
          <div class="card-top"></div>
          <!-- <hr /> -->
          <div class="card-bottom">
            <p class="time">{{ time.seconds }}</p>
          </div>
        </div>
        <p class="time-text">SECONDS</p>
      </div>
    </div>
    <div class="socials">
      <img src="@/assets/icon-facebook.svg" alt="" />

      <img src="@/assets/icon-instagram.svg" alt="" />
      <img src="@/assets/icon-pinterest.svg" alt="" />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'HomeView',
  mounted() {
    this.setTime();
  },
  components: {},
  data() {
    return {
      time: {
        days: '0',
        hours: '0',
        minutes: '0',
        seconds: '0',
      },
    };
  },
  methods: {
    setTime() {
      const finalDate = new Date('Aug 5, 2022 15:37:25').getTime();
      setInterval(() => {
        let now = new Date().getTime();
        let distance = finalDate - now;
        let days = Math.floor(distance / (1000 * 60 * 60 * 24)).toString();
        let hours = Math.floor(
          (distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60)
        ).toString();
        let minutes = Math.floor(
          (distance % (1000 * 60 * 60)) / (1000 * 60)
        ).toString();
        let seconds = Math.floor((distance % (1000 * 60)) / 1000).toString();

        days.length < 2
          ? (this.time.days = '0' + days)
          : (this.time.days = days);

        hours.length < 2
          ? (this.time.hours = '0' + hours)
          : (this.time.hours = hours);

        minutes.length < 2
          ? (this.time.minutes = '0' + minutes)
          : (this.time.minutes = minutes);

        seconds.length < 2
          ? (this.time.seconds = '0' + seconds)
          : (this.time.seconds = seconds);
      }, 1000);
    },
  },
};
</script>

<style scoped>
/* .img {
  position: absolute;
  bottom: 0;
  width: 100%;
}

.img img {
  width: 100%;
}

.second-img {
  position: absolute;
}
.value {
  font-style: normal;
  font-weight: 700;
  font-size: 80px;
  line-height: 71px;

  text-align: center;
  letter-spacing: -2.4px;

  color: #fb5e84;
}

.wrapper {
  text-align: center;
  margin-top: 105px;
}

.time-wrapper {
  display: flex;
  gap: 60px;
  text-align: center;
  margin-left: 35%;
}

h3 {
  font-style: normal;
  font-weight: 700;
  font-size: 22px;
  line-height: 29px;
  text-align: center;
  letter-spacing: 7.5px;
  text-transform: uppercase;

  color: #ffffff;
}

.head {
  margin-top: 132px;
}

.key {
  font-style: normal;
  font-weight: 700;
  font-size: 14px;
  line-height: 19px;
  text-align: center;
  letter-spacing: 5.91875px;
  text-transform: uppercase;
  color: #8385a9;
} */

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.background {
  background-color: hsl(235, 16%, 14%);
  position: absolute;
  height: 100vh;
  width: 100%;
  z-index: -1;
  color: white;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.bgimage-1 {
  position: absolute;
  top: 0;
  z-index: -1;
}
.bgimage-2,
.bgimage-2 img {
  position: absolute;
  bottom: 0;
  width: 100%;
  z-index: -1;
}
.containers {
  display: flex;
  justify-content: space-between;
  width: calc(100% - 752px);
}
.container {
  width: 148px;
}
.card {
  margin-bottom: 26px;
}
.card-top {
  background: #343650;
  opacity: 0.8;
  border-radius: 8px;
  height: 70px;
  width: 100%;
}
.card-bottom {
  background: #343650;
  border-radius: 8px;
  height: 70px;
  width: 100%;
  box-shadow: 0 12px 0px 0 rgba(25, 26, 35, 1);
}
hr {
  background: #000000;
  mix-blend-mode: normal;
  opacity: 0.25;
}
.time-text {
  font-family: 'Red Hat Text';
  font-style: normal;
  font-weight: 700;
  font-size: 14px;
  line-height: 19px;
  text-align: center;
  letter-spacing: 5.91875px;
  color: #8385a9;
}
.time {
  font-family: 'Red Hat Text';
  font-style: normal;
  font-weight: 700;
  font-size: 80px;
  line-height: 71px;
  text-align: center;
  letter-spacing: -2.4px;
  color: #fb5e84;
  position: relative;
  top: -35px;
}
.header-text {
  font-family: 'Red Hat Text';
  font-style: normal;
  font-weight: 700;
  font-size: 22px;
  line-height: 29px;
  text-align: center;
  letter-spacing: 7.5px;
  text-transform: uppercase;
  margin-bottom: 104px;
  color: #ffffff;
}
.socials {
  position: absolute;
  bottom: 72px;
}
.socials img {
  margin-right: 32px;
  cursor: pointer;
}

.socials img:hover {
  background-color: #fb5e84;
}

@media screen and (max-width: 768px) {
  .background {
    overflow: hidden;
  }
  .header-text {
    font-family: 'Red Hat Text';
    font-style: normal;
    font-weight: 700;
    font-size: 18px;
    line-height: 24px;
    text-align: center;
    letter-spacing: 6.13636px;
    text-transform: uppercase;
    color: #ffffff;
  }
  .containers {
    width: calc(100% - 48px);
  }
  .card-top,
  .card-bottom {
    height: 33px;
    width: 70px;
  }
  .time {
    font-family: 'Red Hat Text';
    font-style: normal;
    font-weight: 700;
    font-size: 36px;
    line-height: 71px;
    display: flex;
    align-items: center;
    text-align: center;
    letter-spacing: -1.08px;
    color: #fb5e84;
    left: 15px;
  }
  .time-text {
    font-family: 'Red Hat Text';
    font-style: normal;
    font-weight: 700;
    font-size: 7px;
    line-height: 9px;
    text-align: center;
    letter-spacing: 2.95937px;
    color: #8385a9;
  }
}
</style>
