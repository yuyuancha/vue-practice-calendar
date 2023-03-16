<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <textarea name="textarea_year" id="textarea_year" cols="5" rows="1" v-model="year" maxlength="4" />
    <ul>
      <li v-for="(weekday, index) in weekdays" :key="`day_${index}`">{{ weekday }}</li>
      <li v-for="(weekday, index) in weekdays" :key="`day1_${index}`">{{ weekday }}</li>
      <li v-for="(weekday, index) in weekdays" :key="`day2_${index}`">{{ weekday }}</li>
      <li v-for="(weekday, index) in weekdays" :key="`day3_${index}`">{{ weekday }}</li>
      <li v-for="(weekday, index) in weekdays" :key="`day4_${index}`">{{ weekday }}</li>
    </ul>
  </div>
</template>

<script>
import dayjs from 'dayjs';

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  setup() {
    const weekdays = [
      '一',
      '二',
      '三',
      '四',
      '五',
      '六',
      '日'
    ];

    const year = dayjs().year();
    const firstDate = dayjs(new Date(year, 0, 1));
    console.log(firstDate.year(), firstDate.month(), firstDate.date(), firstDate.day());

    return {
      year,
      weekdays
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline;
  margin: 0 10px;
}

#textarea_year {
  resize: none;
  font-size: 20px;
}
</style>
