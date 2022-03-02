<template>
  <div>
    <h2>Calculator Page</h2>
    <div>
      <input type="text" v-model.number="num1" />
      <input type="text" v-model.number="num2" />
      <button @click="addNum()">Sum</button>
      <p>Answer : {{ ans }}</p>
    </div>

    <br />
    <h2>Num Generator</h2>
    <div>
      <input type="number" v-model.number="myNum" />
      <button @click="displayAllNum()">Display Numbers</button>

      <p v-for="index in conNum" :key="index">{{ index }}</p>

      <p v-for="stud in studentDetails" :key="stud">{{ stud }}</p>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      num1: 4,
      num2: 3,
      ans: 0,
      myNum: 0,
      conNum: 0,
      studentDetails: [],
    };
  },
  methods: {
    addNum() {
      this.ans = this.num1 + this.num2;
    },

    displayAllNum() {
      this.conNum = this.myNum;
    },
  },
  created() {
    fetch("http://localhost:8084/getname")
      .then((data) => {
        //Error Ocurred
        if (!data.ok) {
          throw Error(data.status);
        }
        return data.json();
      })
      .then((update) => {
        //Success
        this.studentDetails = update;
        console.log(update);
      })
      .catch((e) => {
        //Unkonwn Error
        console.log(e);
      });
  },
};
</script>