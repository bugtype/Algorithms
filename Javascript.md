# Algorithms
알고리즘 연습 및 Snippet


```javascript
function isPalindrome(number){
    s = String(number)
    len = s.length

    if (len % 2 ==0){
        console.log(number, false)
        return
    }
    for(let i = 0; i < Math.floor(len/2); i++){
        if (s[i]!=s[len-i-1]){
            console.log(number, false)
            return
        }
    }
    console.log(number, true)

}
isPalindrome(100)
isPalindrome(-100)
isPalindrome(1001)
isPalindrome(10001)
isPalindrome(89894)
isPalindrome(99899)

```


sort 

```javascript
var test = [1,5,3,2,0]
test.sort() // [0, 1, 2, 3, 5]
test.sort( (a,b) => a-b ) // [0, 1, 2, 3, 5]
test.sort( (a,b) => b-a) // [5, 3, 2, 1, 0]

```


// set
```javascript
const arr = [1,3,2,4,3,1,5,6,2,1];
const newArr = [...new Set(arr)];
console.log(arr); // [1,3,2,4,5,6] 중복이 제거된 배열을 얻을 수 있다. Set type입니다.
console.log(convertArr); // [1,3,2,4,5,6] 중복이 제거된 배열을 얻을 수 있다.
```

// n 진수
```javascript
var dec = 123; 
var hex = dec.toString(16);
var oct = dec.toString(8);
```

// es 10 array flat

```javascript
var arr1 = [1, 2, [3, 4]];
arr1.flat(); 
// [1, 2, 3, 4]

var arr2 = [1, 2, [3, 4, [5, 6]]];
arr2.flat();
// [1, 2, 3, 4, [5, 6]]

var arr3 = [1, 2, [3, 4, [5, 6]]];
arr3.flat(2);
// [1, 2, 3, 4, 5, 6]
arr3.flat().flat()
// [1, 2, 3, 4, 5, 6]
```


// Array.flatMap()

```javascript
var arr = [1,2,3,4,5]

arr.map(x => [x,x*2])
// [Array(2), Array(2), Array(2), Array(2), Array(2)]

arr.flatMap( v => [v, v* 2] )
//  [1, 2, 2, 4, 3, 6, 4, 8, 5, 10]
```


// Array ?

``` javascript
var arr = [];
arr.length = 99
cosnole.log(arr)
arr['name'] = 'hello'
console.log(arr.length)  //??
```
