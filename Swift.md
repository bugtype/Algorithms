

### Swift algorithms



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

### ref

regex - https://stackoverflow.com/questions/27880650/swift-extract-regex-matches
