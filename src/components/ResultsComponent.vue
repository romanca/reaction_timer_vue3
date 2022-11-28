<template>
  <p class="reactionTime">Reaction time: {{ score }} ms</p>
  <p class="rank">{{ rank }}</p>
</template>

<script>
export default {
  name: 'ResultsComponent',
  props: ['score'],
  data() {
    return {
      rank: null,
    };
  },
  mounted() {
    this.showRank();
  },
  methods: {
    showRank() {
      if (this.props < 450) {
        this.rank = 'Super fast';
      } else if (this.props < 650) {
        this.rank = 'Fast';
      } else {
        this.rank = 'Slow';
      }
    },
  },
};
</script>

<style>
.reactionTime {
  font-size: 22px;
  color: black;
  font-weight: bold;
}
.rank {
  font-size: 18px;
  color: red;
  font-weight: bold;
}
</style>
