<template>
  <section class="container">
    <div class="content-wrap">
      <div class="card">
        <div class="plan">{{ plan }}</div>
      </div>
      <div class="cp_ipselect cp_sl04">
        <select v-model="plan">
          <option v-for="option in options" v-bind:value="option.value" v-bind:key="option.id">
            {{ option.value }}
          </option>
        </select>
      </div>
      <div class="btn-wrapper">
        <button @click="reset()">リセット</button>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      plan: 1,
      options: []
    };
  },
  mounted: function() {
    for (let i = 1; i < 100; i++) {
      this.options.push({ id: i, value: i });
    }
  },

  methods: {
    reset() {
      this.plan = 1;
    }
  }
};
</script>

<style>
.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
.content-wrap {
  display: flex;
  flex-direction: column;
}
.card {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 200px;
  height: 300px;
  border: 3px solid rgb(52, 190, 219);
  border-radius: 5px;
  box-shadow: 2px 2px 4px grey;
}

.plan {
  font-size: 80px;
  color: rgb(52, 190, 219);
  font-weight: 900;
}

.cp_ipselect {
  overflow: hidden;
  width: 90%;
  margin: 2em auto;
  text-align: center;
}
.cp_ipselect select {
  width: 100%;
  padding-right: 1em;
  cursor: pointer;
  text-indent: 0.01px;
  text-overflow: ellipsis;
  border: none;
  outline: none;
  background: transparent;
  background-image: none;
  box-shadow: none;
  -webkit-appearance: none;
  appearance: none;
  font-size: 24px;
}
.cp_ipselect select::-ms-expand {
  display: none;
}
.cp_ipselect.cp_sl04 {
  position: relative;
  border: 1px solid white;
  border-radius: 20px;
  background: rgb(52, 190, 219);
}
.cp_ipselect.cp_sl04::before {
  position: absolute;
  top: 1.2em;
  right: 0.8em;
  width: 0;
  height: 0;
  padding: 0;
  content: "";
  border-left: 6px solid transparent;
  border-right: 6px solid transparent;
  border-top: 6px solid white;
  pointer-events: none;
}
.cp_ipselect.cp_sl04 select {
  padding: 8px 38px 8px 8px;
  color: white;
}
.btn-wrapper {
  width: 90%;
  margin: auto;
}
button {
  background-color: white;
  border: 1px solid rgb(52, 190, 219);
  color: rgb(52, 190, 219);
  width: 100%;
  border-radius: 20px;
  font-size: 24px;
}
</style>
