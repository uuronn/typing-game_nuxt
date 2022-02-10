<template>
  <div class="typing">
    <div class="typing__group" v-if="isShow">
      <h2 class="typing__question">{{ question }}</h2>
      <!-- <p class="typing__romanAlphabet">{{ question }}</p> -->
      <input class="typing__form" type="text">
      <div class="typing__background" id="keyDown"></div>
      <p class="typing"><span>{{pressed}}</span>{{question}}</p>
      <p>ミスの数は{{missNumber}}</p>
    </div>
    <p class="typing__start" v-if="isEnterOpen">Enterキーを押してスタート</p>
    <NuxtLink to="/" class="typing__link">
      <div class="typing__wrapper">
        <button class="typing__home">ホーム</button>
      </div>
    </NuxtLink>
  </div>
</template>

<script>
import { questions } from './question'

export default {
  data() {
    return {
      isShow: false,
      isEnterOpen: true,
      question: '',
      pressed: "",
      missNumber: '',
      questions: questions,
      timer: 3000
    }
  },
  methods: {
    gameStart(event) {
      if(event.code === "Enter" && this.isEnterOpen === true) {
        setTimeout(() => {
          this.isShow = true;
          this.isEnterClose = false;
        }, this.timer)
        console.log("test")
      } else {
        console.log('ゲーム中')
      }
    },
    typeShow(e) {
      const keyCode = e.code;
      console.log(e.code);
      if (e.code === "Enter") {
        this.isEnterOpen = false;
      } else {
        let keyDown = document.getElementById('keyDown');
        const myCode = String.fromCharCode(keyCode);
        let myCodeLower = myCode.toLowerCase();
        keyDown.innerHTML += myCodeLower;
      }
    },
    setWord() {
      this.question = this.questions.splice(Math.floor(Math.random()*this.questions.length),1)[0];
    },
    keyDown(){
      addEventListener('keydown',e => {
        if(e.key !== this.question[0]){
          this.missNumber ++;
          return;
        }
        this.pressed += e.key;
        this.question = this.question.slice(1);
        if(this.question.length == 0) {
          this.pressed = '';
          this.setWord();
          if(this.questions.length == 0) {
            this.question = '終了です';
            return;
          }
        }
      });
    }
  },
  mounted() {
    this.keyDown();
    this.setWord();
    addEventListener('keydown', this.gameStart);
    addEventListener('keydown', this.typeShow);
  },
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
    margin-top: 300px;
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

  span {
    color: red;
  }
}
</style>
