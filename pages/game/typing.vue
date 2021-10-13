<template>
  <div class="typing">
    <div class="typing__group">
      <h2 class="typing__question">{{ questions[0].question }}</h2>
      <p class="typing__romanAlphabet">{{ questions[0].romanAlphabet }}</p>
    </div>
    <input class="typing__form" v-model="typeBox" type="text">
    <p class="typing__start">Enterキーを押してスタート</p>
    <NuxtLink to="/" class="typing__link">
      <button class="typing__home">ホーム</button>
    </NuxtLink>
  </div>
</template>

<script>
export default {
  data() {
    return {
      typeBox: "",
      questions: [
        {
          question: "ここに問題",
          romanAlphabet: "kokonimondai"
        },
        {
          question: "無人島",
          romanAlphabet: "mujinto"
        },
        {
          question: "プログラミングは難しい",
          romanAlphabet: "programinghamuzukasi"
        },
      ]
    }
  },
  methods: {
    gameStart(event) {
      if(event.code === "Enter") {
        alert("test")
        console.log("test")
      } else {
        console.log("失敗")
      }
    }
  },
  mounted() {
    document.addEventListener('keydown', this.gameStart);
  },
  watch: {
    typeBox(e) {
      if (e == this.questions[0].romanAlphabet) {
        alert("ゲームスタート")
        console.log("test")
      }
    },
  }
}
</script>

<style lang="scss" scoped>
.typing {
  text-align: center;
  background: $ui-main;
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
    top: 0;
    right: 0;
  }

  &__home {
    
  }
}
</style>
