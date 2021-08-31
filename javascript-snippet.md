


알파벳 체크

```javascript
function isAlphabet(st) {
  return /[a-zA-Z]/.test(st);
}
function isLetter(str) {
  return str.length === 1 && str.match(/[a-z]/i);
}
if( char.toUpperCase() != char.toLowerCase() ) 


```


중복 글자, 확인 및 제거

```javascript
let strArray = [ "q", "w", "w", "w", "e", "i", "u", "r"];
let findDuplicates = arr => arr.filter((item, index) => arr.indexOf(item) != index)

console.log(findDuplicates(strArray)) // All duplicates
[
  "w",
  "w"
]
console.log([...new Set(findDuplicates(strArray))]) // Unique duplicates
[
  "w",
]
```


### 투포인터

- 구간합 https://taesung1993.tistory.com/12


```javascript
const arr = [1, 2, 3, 2, 5];
let answerNum = 0;
let start = 0;
let end = 0;
let loopCount = 0;
let result = 0;

while(arr[start] !== undefined){
  while(result < 5 && end < arr.length){
    result += arr[end];
    end++;
  }
  if(result === 5)
    answerNum++;
  result -= arr[start];
  start++;
  loopCount++;
}

console.log("정답 개수:", answerNum); // 정답개수: 3
console.log("연산 횟수:", loopCount); // 연산횟수: 5
```

### preSum 

```javascript
function solution(l, r, arr) {
  let sum = 0;
  const p = [0];

  for (let i = 0; i < arr.length; i++) {
    sum += arr[i];
    p.push(sum);
  }

  return p[r] - p[l - 1];
}
const arr = [10, 20, 30, 40, 50];
console.log(solution(2, 5, arr));
```


숫자 문자열 영단어

- https://programmers.co.kr/learn/courses/30/lessons/81301

one4seveneight -> 1478

```javascript
function solution(s) {
    var answer = 0;
    const word = {
        zero: 0,
        one: 1,
        two: 2,
        three: 3,
        four: 4,
        five: 5,
        six: 6,
        seven: 7,
        eight: 8,
        nine: 9,
    }
    const words = Object.keys(word).join("|")
    const regexp2 = new RegExp(`${words}|[0-9]`, 'g')
    const result = s.match(regexp2).map(v => word[v]===undefined ? v : word[v] ).join("")

    
    return Number(result);
}



function solution(s) {
    let numbers = ["zero", "one", "two", "three", "four", "five", "six", "seven", "eight", "nine"];
    var answer = s;

    for(let i=0; i< numbers.length; i++) {
        let arr = answer.split(numbers[i]);
        answer = arr.join(i);
    }

    return Number(answer);
}


function solution(s) {
    s = s.replace(/zero/gi, 0)
    .replace(/one/gi, 1)
    .replace(/two/gi, 2)
    .replace(/three/gi, 3)
    .replace(/four/gi, 4)
    .replace(/five/gi, 5)
    .replace(/six/gi, 6)
    .replace(/seven/gi, 7)
    .replace(/eight/gi, 8)
    .replace(/nine/gi, 9)
    return parseInt(s);
}

```