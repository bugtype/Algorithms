# Algorithms
알고리즘 연습 및 Snippet




### isPalindrome

```javascript


function isPalindrome(number){
   
    if(number < 0){
        return false;
    }
    
    if(number < 10){
        return true;
    }
   
    
    const s = number.toString();

    for(let i = 0; i<Math.floor(s.length/2);i++){
        if(s[i] !== s[s.length-i-1]){
            return false;
        }    
    }
    return true;

}

var isPalindrome = function(x) {
    let current = x;
    let result = 0;

    while (current > 0) {
        result = result * 10 + current % 10;
        current = Math.floor(current / 10);
    }

    return result === x;
};


isPalindrome(100)
isPalindrome(-100)
isPalindrome(1001)
isPalindrome(10001)
isPalindrome(89894)
isPalindrome(99899)

```

### twoSum

```javascript

var twoSum = function(nums, target) {
    const map = new Map();
    for (let i = 0; i < nums.length; i++) {
        const num = nums[i];
        const diff = target - num;
        if (map.has(diff)) return [map.get(diff), i];
        map.set(num, i);
    }
};

```

### reverse Integer

```javascript

var reverse = function(x) {
    let pos = false;
    const upperB=Math.pow(2,31)-1;
    const lowerB=-Math.pow(2,31);
    if(x<0){
        pos=true;
        x*=-1;
    }
    const n = Number((""+x).split("").reverse("").join(""));
    return pos ? -1*n : n;
};

```


### roman to integer

- https://leetcode.com/problems/roman-to-integer/

```javascript
var romanToInt = function(s) {
    
	let sumArr = []
	let total = 0

	for (let i = 0; i < s.length; i++) {

		switch (s[i]) {

			case "I":
				sumArr.push(1)
				break
			case "V":
				sumArr.push(5)
				break
			case "X":
				sumArr.push(10)
				break
			case "L":
				sumArr.push(50)
				break
			case "C":
				sumArr.push(100)
				break
			case "D":
				sumArr.push(500)
				break
			case "M":
				sumArr.push(1000)
				break

		}

	}

	sumArr.forEach((v,i) => {

		if (i == 0) {
			total += v
			return
		}

		if (sumArr[i-1] < v) {
			total += v-sumArr[i-1]*2
			return
		}

		total += v

	})

	return total
};
```


14. Longest Common Prefix

- https://leetcode.com/problems/longest-common-prefix/ 


```javascript

var longestCommonPrefix = function(strs) {
    let prefix = '';
    if (strs.length === 1) return strs[0];
    for (let i = 0; i < strs[0].length; i++) {
        let currentChar = strs[0][i];
        if (currentChar && strs.every((s) => s[i] == currentChar)) {
            prefix += currentChar;
        } else {
            return prefix;
        }
    }
    
    return prefix;
};



```


### Valid Parentheses


- https://leetcode.com/problems/valid-parentheses/

```javascript

var isValid = function(s) {
    let stack = []
    const map = new Map()
    map.set("(", ")")
    map.set("{", "}")
    map.set("[", "]")
    
    for (element of s) {
        if (map.has(element)) { // open
            stack.push(element)
        } else {                            // close
            const lastOpen = stack.pop()
            if (element !== map.get(lastOpen)) {
                return false
            }
        }
    }
    
    return stack.length ? false : true
};

```


26. Remove Duplicates from Sorted Array

- https://leetcode.com/problems/remove-duplicates-from-sorted-array/

```javascript

function removeDuplicates(nums, point = 0) {
  const cursor = nums.lastIndexOf(nums[point]) + 1;

  if (cursor >= nums.length) return point + 1;

  if (cursor !== point) {
    nums[++point] = nums[cursor];
  }

  return removeDuplicates(nums, point);
}

function removeDuplicates(nums) {
  for (let i = 0; i < nums.length; i++) {
    nums.splice(i, nums.lastIndexOf(nums[i]) - i);
  }

  return nums.length;
}

```




rotation

```javascript

function solution(A, K) {
    K = K % A.length;
    const sliceIndex = A.length - K;
    return [...A.slice(sliceIndex), ...A.slice(0, sliceIndex)]
 }

function solution(A, K) {
  if (A.length === 0) return A;
  for (let i = 0; i < K; i++) {
    A.unshift(A.pop());
  }
  return A;
}

 solution([1,2,3,4],1) // [4, 1, 2, 3]
 solution([1,2,3,4],2) // [3, 4, 1, 2]

```


```javascript




    for (let element of A) {
        // Apply Bitwise XOR to the current and next element
        result ^= element
    }

 solution([1,2,3,4],1) // [4, 1, 2, 3]
 solution([1,2,3,4],2) // [3, 4, 1, 2]

```
