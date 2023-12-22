<template>
  <div>
    HEEEELOOLLOL!(()) 
  </div>
  <p>{{ text1 }}</p>
  <p>{{ text2 }}</p>
  <p v-if="visible">Hidden</p>
  <img v-bind:src="attr" class="img">
  <ul>
    <!-- <li>{{arr[0]}}</li>
    <li>{{arr[1]}}</li>
    <li>{{arr[2]}}</li>
    <li>{{arr[3]}}</li> -->
    <li v-for="elem in arr" :key="elem">{{ elem**2 }}</li>
  </ul>
  <p>{{ fulltext }}</p>
  <button @click="show(this.text1)">Do smthng</button>
  <button @click="show(this.text2)">Do smthng2</button>
  <button @click="change">change smthng</button>
  <button @click="addMas">add smthng</button>
  <button @click="visibleChange">{{visible ? "Hide" : "Show"}}</button>
  <p v-show="text1 != 111">Now smtnh change...</p>
  <input type="text" v-model="msg">
  <p>{{ msg }}</p>

</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      text1: '111',
      text2: 222,
      attr: '../assets/1.jpg',
      arr: [1,2,3,4],
      visible: true,
      msg: "hello",
    }
  },
  computed: {
    fulltext: function () {
      return this.text1 + " " + this.text2;
    }
  },
  methods: {
    show: function (str) {
      alert(str);
    },
    change: function () {
      this.text1 = "HEHEHHEEH";
    },
    visibleChange: function () {
      this.visible = !this.visible;
    },
    addMas: function () {
      this.arr.push(99);
    }
  }
}
</script>

<style>
.img {
  width: 300px;
  height: 300px;
}
</style>
