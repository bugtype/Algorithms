



이진 탐색 코드


```javascript

function binarySearch(sortedArray, seekElement) {
  let startIndex = 0;
  let endIndex = sortedArray.length - 1;

  while (startIndex <= endIndex) {
    const middleIndex = startIndex + Math.floor((endIndex - startIndex) / 2);
    if (sortedArray[middleIndex] === seekElement) {
      return middleIndex;
    }
    if (sortedArray[middleIndex] < seekElement) {
      startIndex = middleIndex + 1;
    } else {
      endIndex = middleIndex - 1;
    }
  }

  return -1;
}

const nums = [10, 40, 50, 30, 60, 70, 80, 90, 20];
const sortedNums = nums.sort();

console.log(binarySearch(sortedNums, 30));
> 2

console.log(binarySearch(sortedNums, 100));
> -1
```


DFS

```javascript

function solution(numbers, target) {
    let answer = 0;
    getAnswer(0,0);
    function getAnswer(x,value) {
        if(x<numbers.length){
            getAnswer(x+1,value + numbers[x]);
            getAnswer(x+1,value - numbers[x]);
        } else{
            if(value === target){
                answer++
            }
        }
    }
    return answer;
}
```


DFS 2


```javascript

function solution(n, computers) {
    var answer = 0;
    var isVisited = [];

    for(var i =0; i <n; i++) {
        isVisited.push(false);
    }

    var DFS = function(computers, i) {
        console.log('DFS excuted');
        if(isVisited[i]) { return; }
        isVisited[i] = true;
        console.log(isVisited);

        for(var j = 0; j < computers.length; j++) {
            if(computers[i][j] === 1) {
                console.log(i + ', ' + j);
                console.log('connected');
                DFS(computers, j);
            }
        }
    }

    for(var i = 0; i < n; i++) {
        if(!isVisited[i]) {
            answer++;
            console.log(isVisited, '도입부');
            console.log(answer);
            DFS(computers, i);
        }
    }

    return answer;
}
```