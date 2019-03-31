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