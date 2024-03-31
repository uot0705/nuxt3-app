<script setup lang="ts">
// flatは要素内の配列を全部同じ階層にしてくれる
const arr1 = [0, 1, 2, [3, 4]];

console.log(arr1.flat());
// expected output: [0, 1, 2, 3, 4]

// flatMapは、mapした要素内で配列がネストされたら、要素内の配列を全部同じ階層にしてくれる

// ↓↓応用
const answer1 = [1];
const answer2 = [1];
const answer3 = [0, 1, 2];

const data = [
  { id: 1, answer: answer1 },
  { id: 2, answer: answer2 },
  { id: 3, answer: answer3 },
];

const format = () => {
  const formatData = data.flatMap((item) => {
    return item.answer.map(answer => ({
      id: item.id,
      answer: answer,
    }));
  });
  console.log(formatData);
  /* 本来3配列になっているのを階層を統一してくれる
    0: {id: 1, answer: 1}
    1: {id: 2, answer: 1}
    2: {id: 3, answer: 0}
    3: {id: 3, answer: 1}
    4: {id: 3, answer: 2}
  */
};

format();

// （({})と{}の違い
// 1. 関数で単一の値を返す場合（()や{}不要）
const double = (x: number) => x * 2;
console.log(double(4)); // 8

// 2. 関数でオブジェクトリテラルを直接返す場合（({})使用）
const toObject = (x: number) => ({ value: x * 2 });
console.log(toObject(4)); // { value: 8 }

// 3. 複数の処理を行い、最終的に値を返す場合（{}使用、return必要）
const calculateAndLog = (x: number) => {
  const num = 2;
  const result = x * num;
  return result;
};
console.log(calculateAndLog(4));
</script>