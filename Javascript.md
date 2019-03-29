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