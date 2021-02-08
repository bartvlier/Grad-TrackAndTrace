<template>
  <div class="header-wrapper">
    <div class="header-content">
      <h1>Bedankt voor je bestelling!</h1>
      <h2 class="gradient-text">Coolblue</h2>
      <p>
        Klik de stappen aan waar jij van op de hoogte gehouden wilt worden. geen
        zin om te kiezen? Je kunt altijd een pre-set aanklikken. Wanneer je geen
        keuze maakt ontvang je de standaard updates.
      </p>
      <div class="glass-button-group">
        <router-link to="/about" class="glass-button"
          >Overslaan
          <svg
            width="16"
            height="16"
            viewBox="0 0 16 16"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M15.7071 8.70711C16.0976 8.31658 16.0976 7.68342 15.7071 7.29289L9.34315 0.928932C8.95262 0.538408 8.31946 0.538408 7.92893 0.928932C7.53841 1.31946 7.53841 1.95262 7.92893 2.34315L13.5858 8L7.92893 13.6569C7.53841 14.0474 7.53841 14.6805 7.92893 15.0711C8.31946 15.4616 8.95262 15.4616 9.34315 15.0711L15.7071 8.70711ZM0 9H15V7H0V9Z"
              fill="#C9E4FE"
            /></svg
        ></router-link>
      </div>
    </div>
  </div>
  <div class="content">
    <optionsBar></optionsBar>
    <div class="nextBtnWrapper">
      <div class="nextBtn">
        <router-link to="/about">Volgende</router-link>
        <svg
          width="16"
          height="16"
          viewBox="0 0 16 16"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M15.7071 8.70711C16.0976 8.31658 16.0976 7.68342 15.7071 7.29289L9.34315 0.928932C8.95262 0.538408 8.31946 0.538408 7.92893 0.928932C7.53841 1.31946 7.53841 1.95262 7.92893 2.34315L13.5858 8L7.92893 13.6569C7.53841 14.0474 7.53841 14.6805 7.92893 15.0711C8.31946 15.4616 8.95262 15.4616 9.34315 15.0711L15.7071 8.70711ZM0 9H15V7H0V9Z"
            fill="#FFF"
          />
        </svg>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

import optionsBar from "@/components/molecules/optionsBar.vue";
export default {
  name: "Home",
  components: {
    optionsBar
  },
  mounted() {
    console.log(this.$refs.stagePicked);
  }
};
</script>

<style lang="scss" scoped>
.header-wrapper {
  width: 100%;
  display: flex;
  justify-content: center;
  margin-bottom: 18px;

  .header-content {
    width: 50%;

    p {
      width: 70%;
      color: #6e7191;
    }

    .glass-button {
      display: flex;
      align-items: center;
      color: #c9e4fe;
      text-decoration: none;

      svg {
        margin-left: 10px;
      }

      &:visited {
        color: #c9e4fe;
        text-decoration: none;
      }
    }
  }
}
.content {
  display: flex;
  flex-direction: column;
  align-items: center;

  .nextBtnWrapper {
    margin-top: 35px;
    display: flex;
    justify-content: flex-end;
    align-items: center;
    width: 66%;

    .nextBtn {
      display: flex;
      align-items: center;
      padding: 10px;
      border-radius: 10px;
      background-color: #0379e7;

      a {
        color: white;
        text-decoration: none;
      }

      svg {
        margin-left: 10px;
      }
    }
  }
}
</style>
