<template>
  <div class="hello">
    {{totalrun}} | {{ball}}
    <div class="run">
      <h3>Runs</h3>
      <ul>
        <li v-for="(run,index) in runs" :key="index">
          <button @click="ballcount(), runcount()">{{run.run}}</button>
        </li>
      </ul>
    </div>
    <div>
      <ul>
        <li v-for="(norun,index) in noRuns" :key="index">
          <button class="norun" @click="ballcount(),matchover(norun)">{{norun.value}}</button>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      ball: 0,
      totalrun: 0,
      over: 0,
      runs: [
        { run: 1 },
        { run: 2 },
        { run: 3 },
        { run: 4 },
        { run: 5 },
        { run: 6 }
      ],
      noRuns: [
        { value: "Bowled" },
        { value: "Run Out" },
        {
          value: "Caught"
        },
        {
          value: "Stumps"
        },
        {
          value: "Dot ball"
        }
      ]
    };
  },

  methods: {
    ballcount() {
      this.ball++;
    },
    runcount() {
      this.totalrun++;
    },
    matchover(norun) {
      for (var i = 0; i < this.noRuns.length; i++) {
        if (norun.value !== "Dot ball") {
          alert("Match Over");
          break;
        }
      }
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.norun button {
  background-color: #e00c0c; /* Green */
  border: none;
  color: white;
  padding: 10px 22px;
  text-align: center;
  display: inline-block;
  font-size: 16px;
}
button {
  background-color: #4caf50; /* Green */
  border: none;
  color: white;
  padding: 10px 22px;
  text-align: center;
  display: inline-block;
  font-size: 16px;
}
</style>
