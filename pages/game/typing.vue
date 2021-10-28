<template>
  <div class="typing">
    <div class="typing__group" v-if="isShow">
      <h2 class="typing__question">{{ questions[0].question }}</h2>
      <p class="typing__romanAlphabet">{{ questions[0].romanAlphabet }}</p>
      <input class="typing__form" v-model="typeBox" type="text">
      <div class="typing__background" id="keyDown"></div>
    </div>
    <p class="typing__start" v-if="isEnterClose">Enterキーを押してスタート</p>
    <NuxtLink to="/" class="typing__link">
      <div class="typing__wrapper">
        <button class="typing__home">ホーム</button>
      </div>
    </NuxtLink>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isShow: false,
      isEnterClose: true,
      typeBox: "",
      questions: [
        {
          question: "ここに問題",
          romanAlphabet: "kokonimondai"
        },
        {
          question: "テスト",
          romanAlphabet: "tesuto"
        },
        {
          question: "プログラミングは難しい",
          romanAlphabet: "puroguraminguhamuzukasii"
        },
      ]
    }
  },
  methods: {
    gameStart(event) {
      if(event.code === "Enter" && this.isEnterClose === true) {
        this.isShow = true;
        this.isEnterClose = false;
        console.log("test")
      } else {
        console.log('ゲーム中')
      }
    },
    typeShow(e) {
      const keyCode = e.code;
      console.log(e.code);
      if (e.code === "Enter") {
        console.log("Enter押しました")
      } else {
        let keyDown = document.getElementById('keyDown');
        const myCode = String.fromCharCode(keyCode);
        let myCodeLower = myCode.toLowerCase();
        keyDown.innerHTML += myCodeLower;
      }
    }
  },
  mounted() {
    document.addEventListener('keydown', this.gameStart);
    document.addEventListener('keydown', this.typeShow);
  },
  watch: {
    typeBox(e) {
      if (e === this.questions[0].romanAlphabet) {
        alert("test")
        console.log("test")
      }
    },
  }
}
</script>

<style lang="scss" scoped>
.typing {
  text-align: center;
  background: #674598;
  height: 100vh;
  padding: 10px;

  &__question {
    margin: 40px 0 10px;
    font-size: 80px;
  }

  &__romanAlphabet {
    font-size: 20px;
  }

  &__form {
    background: $font-gray;
    border-bottom: 2px solid #000;
  }

  &__background {
    background: green;
  }

  &__start {
    font-size: 20px;
    margin-top: 100px;
    animation: flash 2s linear infinite;

    @keyframes flash {
      0% {
        opacity: 1;
      }

      50% {
        opacity: 0.3;
      }

      100% {
        opacity: 1;
      }
    }
  }

  &__link {
    position: absolute;
    z-index: 1;
    top: 8px;
    right: 8px;
    text-decoration: none;
  }

  &__wrapper {
    position: relative;
    width: 150px;
    height: 50px;
    display: flex;
    justify-content: center;
    align-items: center;
    background: rgba(0,0,0,0.5);
    overflow: hidden;
    border-radius: 10px;

  
    &:hover:before {
      content: '';
      position: absolute;
      width: 120%;
      height: 30%;
      background: linear-gradient(#00ccff, #d400d4);
      animation: animate 4s linear infinite;
    }

    &::after {
      content: '';
      position: absolute;
      inset: 4px;
      background: $ui-gray;
      border-radius: 7px;
    }

    @keyframes animate {
      0% {
        transform: rotate(0deg);
      }
      100% {
        transform: rotate(720deg);
      }
    }
  }

  &__home {
    position: relative;
    z-index: 10;
    font-size: 18px;
    color: #000;
  }
}
</style>
