<script setup lang="ts">
const data = [
  { id: 1, score: 10 },
  { id: 1, score: 50 },
  { id: 1, score: 100 },
];

const totalScore = data.reduce((total, data) => total + data.score, 0);
console.log(totalScore); // 160

type Totals = {
  [category: string]: number;
};

const items = [
  { category: "食品", price: 100 },
  { category: "食品", price: 150 },
  { category: "雑貨", price: 200 },
];

const totalByCategory = items.reduce<Totals>((totals, item) => {
  const { category, price } = item;
  if (!totals[category]) {
    totals[category] = 0;
  }
  
  totals[category] += price;
  return totals;
}, {});

console.log(totalByCategory); // { 食品: 250, 雑貨: 200 }
</script>
