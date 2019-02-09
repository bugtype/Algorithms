

### Swift algorithms


### flatmap

```swift
var str = "Hello, playground"

let numbers = [[1,2,3],[4],[5,6,7,8,9]]
let flattened = Array(numbers.joined())
let flatMapItems = numbers.flatMap { $0 }

print(numbers)
print(flattened)
print(flatMapItems)

[[1, 2, 3], [4], [5, 6, 7, 8, 9]]
[1, 2, 3, 4, 5, 6, 7, 8, 9]
[1, 2, 3, 4, 5, 6, 7, 8, 9]

```

### regex

```swift
func solution(_ phone_number:String) -> Int {
        let patterns = [
         "^010-[0-9]{3,4}-[0-9]{3,4}",
         "^010[0-9]{7,8}",
         "^(\\+82-10-)[0-9]{3,4}-[0-9]{3,4}",
        ]
    let fullRange = NSMakeRange(0, phone_number.count)
    for i in 0...patterns.count - 1 {
        let pattern = patterns[i]
        guard let regex = try? NSRegularExpression(pattern: pattern, options: []) else { return 0 }
        let n = regex.numberOfMatches(in:phone_number, options:[], range:fullRange)
        if n > 0 { return i + 1}
    }
    return 0
}

```

### formula / Recurrence relation

```swift
// An = An-1 + An-2
func recur(num: Int)->Int{
    if num <= 1 { return 1 }
    return recur(num: num-1) + recur(num: num-2)
}
print(recur(num: 5))
```

### ref

regex - https://stackoverflow.com/questions/27880650/swift-extract-regex-matches
