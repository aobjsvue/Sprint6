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
          { story: "El nostre heroi estava surant per l'espai sideral quan a la llunyania va albirar una nau espacial." },
          { story: "Sentia curiositat per l'interior de la nau i es va posar a inspeccionar-la. Va arribar a una sala amb dues portes." },
          { story: "L'heroi va decidir travessar la porta que el portava a casa." },
          { story: "Mentrestant, altres herois no van tenir tanta sort en la seva elecció..."}
        ],
        currentSentence: 0
      }
    },
    methods: {
      previousSentence() {
        if (this.currentSentence == 0) {
          this.currentSentence = 3;
        } else {
          this.currentSentence--;
        }
      },
      nextSentence() {
        if (this.currentSentence == 3) {
          this.currentSentence = 0;
        } else {
          this.currentSentence++;
        }
      }
    }
  }
</script>

<template>
  <div>
    <Buttons @previousSentence="previousSentence" @nextSentence="nextSentence"></Buttons>
    <Scene :arrayText="arrayText" :currentSentence="currentSentence"></Scene>
  </div>
</template>

<style>
  
</style>
