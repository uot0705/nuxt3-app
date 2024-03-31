<script setup lang="ts">
const data = [
  { id: 1, status: 1, check: false },
  { id: 2, status: 1, check: true },
  { id: 3, status: 2, check: false },
  { id: 4, status: 1, check: true },
];

// 指定した条件の最初のindexを返す
const findIndex = data.findIndex(data => data.status === 1);
console.log(findIndex); // 0

// 指定した条件の最初の要素だけを返す
const find = data.find(data => data.status === 1);
console.log(find); // {id: 1, status: 1, check: false}

// 指定した条件で新しい配列を作成(指定した条件の全ての要素を返す)
const filter = data.filter(data => data.check === true);
console.log(filter);
/*
0: {id: 2, status: 1, check: true}
1: {id: 4, status: 1, check: true}
*/

// 指定した条件が満たすか(一つでもあれば)どうかをbooleanで返す
const some = data.some(data => data.status === 3);
console.log(some); // false

// 指定した条件がすべての要素で満たすかどうかをbooleanで返す
const every = data.every(data => typeof data.status === 'number');
console.log(every); // true

// statusが1でcheckがtureのものだけ返す
const test = () => {
  const filter = data.filter(data => data.status === 1 && data.check === true);
  console.log(filter);
};
/*
0: {id: 2, status: 1, check: true}
1: {id: 4, status: 1, check: true}
*/
test();
</script>