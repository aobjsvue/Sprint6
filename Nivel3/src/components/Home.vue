<script>
  import Scene from './Scene.vue';
  import Buttons from './Buttons.vue';

  export default {
    name: "Home",
    components: {
      Scene,
      Buttons
    },
    data() {
      return {
        arrayText: [
          { txt: "El nostre heroi estava surant per l'espai sideral quan a la llunyania va albirar una nau espacial.", img: '../src/assets/img/1.jpg' },
          { txt: "Sentia curiositat per l'interior de la nau i es va posar a inspeccionar-la. Va arribar a una sala amb dues portes.", img: '../src/assets/img/2.jpg' },
          { txt: "L'heroi va decidir travessar la porta que el portava a casa.", img: '../src/assets/img/3.jpg' },
          { txt: "Mentrestant, altres herois no van tenir tanta sort en la seva elecció...", img: '../src/assets/img/4.jpg'}
        ],
        currentSentence: 0,
        sceneVisibility: false
      }
    },
    methods: {
      previousSentence() {
        if (this.currentSentence <= 0) {
          this.currentSentence = 3;
          document.body.style.backgroundImage = "url(" + this.arrayText[this.currentSentence].img + ")";
        } else {
          this.currentSentence--;
          document.body.style.backgroundImage = "url(" + this.arrayText[this.currentSentence].img + ")";
        }
      },
      nextSentence() {
        if (this.currentSentence >= 3) {
          this.currentSentence = 0;
          document.body.style.backgroundImage = "url(" + this.arrayText[this.currentSentence].img + ")";
        } else {
          this.currentSentence++;
          document.body.style.backgroundImage = "url(" + this.arrayText[this.currentSentence].img + ")";
        }
      },
      toggleVisibility() {
        this.sceneVisibility = !this.sceneVisibility;
        if (this.sceneVisibility) {
          document.body.style.backgroundImage = "url('../src/assets/img/1.jpg')";
          this.currentSentence = 0;
        } else {
          document.body.style.backgroundImage = "url('../src/assets/img/0.jpg')";
        }
      }
    }
  }
</script>

<template>
  <div>
    <div class="welcome">
      <h2>Benvingut/da!</h2>
      <h4>Descripció del projecte</h4>
      <button class="btn-start" @click="toggleVisibility">Iniciar / Sortir</button>
    </div>
    <div v-if="sceneVisibility" >
      <Buttons @previousSentence="previousSentence" @nextSentence="nextSentence" ></Buttons>
      <Scene :arrayText="arrayText" :currentSentence="currentSentence"></Scene>
    </div>
  </div>
</template>

<style>
  .welcome {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .btn-start {
    margin-top: 2em;
  }
  h2 {
    color: white;
  }
  h4 {
    color: white;
  }
</style>
