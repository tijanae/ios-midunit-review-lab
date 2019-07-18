## Mid Unit-1 Review


## Strings

1. **Given a String, return a String with each letter uppercased**

Input: `Hello, there`

Output: `HELLO, THERE`

```
var input = "Hello, there"

var output = input.uppercased()
print(output)
```

2. **Given a String, return a String alternating between uppercase and lowercase letters**


Input: `Hello, there`

Output: `HeLlO, tHeRe`

```
var input = "Hello, there"

var output = ""

for (i, c) in input.enumerated() {
if i % 2 == 0 {
output.append(c.uppercased())
}
else{
output.append(c.lowercased())
}
}

print(output)
```


3. **Given a String, return a String with all occurrences of a given letter removed**

Input: `Hello, there`

Output: `Hllo, thr`

```
var input = "Hello, there"

var output = ""
var letter = "e"

for c in input where String(c) != letter {
output.append(c)
}
```


## Arrays


1. **Given an array of type [Int], return the largest element**

Input: `[1,5,2,4,1,4]`

Output: `5`

```
var input = [1,5,2,4,1,4]

var output = 0


for int in input{
if int > output{
output = int
}
}

print(output)
```

2. **Given an array of type [Int], return the smallest element**

Input: `[1,5,2,4,1,4]`

Output: `1`

```
var input = [1,5,2,4,1,4]

var output = 5


for int in input{
if int < output{
output = int
}
}

print(output)
```

3. **Given an array of type [Int], return its sum**

Input: `[1,5,2,4,1,4]`

Output: `17`

```
var input = [1,5,2,4,1,4]

var output = 0

for i in input{
output += i
}

print(output)
```

4. **Given an array of type [Double], return its average**

Input: `[3,4.5,7.5,2,1]`

Output: `3.6`

```
var input = [3,4.5,7.5,2,1]

var output = 0.0

for i in input{
output += i
}
var average = (output / Double(input.count))

print(average)
```

5. **Given an array of type [Double] and a Double, return the sum of all numbers in the array greater than a given number**

Input: `[3,4.5,7.5,2,1], 3`

Output: `12`

```
var input = [3,4.5,7.5,2,1]
var givenNumber = 3

var output = 0.0

for i in input {
if i > Double(givenNumber){
output += i
}
}

print(output)
 
```


6. **Given an array of type [Double], return the product of all the elements**

Input: `[3,4.5,7.5,2,1]`

Output: `202.5`

```
var input = [3,4.5,7.5,2,1]
var product = 1.0

for number in input {
product *= number
}
print(product)
```



7. **Given an array of type [Int], return the second smallest value in the array**

Input: `[3,6,1,9,4,8]`

Output: `3`
```
var input = [3,6,1,9,4,8]

input.sort()
print(input[1]) 
```

## Optionals

1. **Given an array of type [String?] return an array of [String] removing all nil values**

Input: `[nil, "We", "come", nil, "in", "peace"]`

Output: `["We", "come", "in", "peace"]`

```
var input = [nil, "We", "come", nil, "in", "peace"]
var output: [String] = []
​
​for index in input where index != nil {
​if let index = index {
​output.append(index)
​}
​}
​print(output)
```

2. **Given an array of type [String?]? return an array of [String] removing all nil values**

Input: `nil`

Output: `[]`

```
var input: [String?] = [nil]
var output: [String] = []

for i in input where i != nil {
if let index = i {
output.append(i!)
}
}
print(output)
```

3. **Given an array of type [Int?] return the sum of all non-nil values.  Use guard statements in your solution.**

Input: `[4, nil, 9, 5, nil]`

Output: `18`

```
func sumOfAllNonNilValues(in arr: [Int?]) -> Int {
var sum = 0
for element in arr {
guard let unwrappedElement = element else { continue }
sum += unwrappedElement
}
return sum
}
sumOfAllNonNilValues(in: [4, nil, 9, 5, nil])
```

!!!!!4. **Given an array of type [Int?]? return the sum of all non-nil values.  Use guard statements in your solution.**

Input: `nil`

Output: `0`
```
func sumOfAllNonNilValues(in arr: [Int?]) -> Int {
var sum = 0
for element in arr {
guard let unwrappedElement = element else { continue }
sum += unwrappedElement
}
return sum
}
sumOfAllNonNilValues(in: [nil])

print(sumOfAllNonNilValues(in: [nil]))
```

5. **Given an array of type [Int?] and an optional Int, return the sum of all values not equal to the given number.  If the given number is nil, return the sum of all non-nil values.**

Input: `[1, 1, nil, 3, 5, nil, 1, nil, 3, 5, nil, 5, nil, 3], 1`

Output: `24`
```
var array = [1, 1, nil, 3, 5, nil, 1, nil, 3, 5, nil, 5, nil, 3]
var givenNUmber = 1
var sum = 0

for number in array where number != nil && number != givenNUmber {
sum += number ?? 0
}
print(sum)
```

## Dictionaries

1. **Given an array of type [String], return a copy of the array with all duplicate values removed**

Input: `["apple", "apple", "banana", "banana", "banana", "cake", "cake"]`

Output: `["apple", "banana", "cake"]`
```
var input = ["apple", "apple", "banana", "banana", "banana", "cake", "cake"]

var noDupes = Set(input)

print(noDupes)
```

2. **Given a String, find the most frequently occurring letter**

Input: `Never trust a computer you can't throw out a window ~ Steve Wozniak`

Output: `t`

```
var myString = "Never trust a computer you can't throw out a window ~ Steve Wozniak"
//Output: `t`

var freqDict = [Character: Int]()
var mostFrequent:Character = " "

var count:Int = 0

for c in myString where c != " "{
if freqDict.keys.contains(c) {
freqDict[c] = freqDict[c]! + 1
} else {
freqDict[c] = 1
}

if let helperVariable = freqDict[c] {
if helperVariable > count{
mostFrequent = c
count = helperVariable
}
}
}
print(mostFrequent)
```

3. **Given an array of type [Int], return a copy of the array that contains only elements that appear at least twice**

Input: `[1,1,2,3,3,3,4,5,6,6,7]`

Output: `[1,3,6]`
```
var numbers = [1,1,2,3,3,3,4,5,6,6,7]
var freqDict = [Int: Int]()
var newArray: [Int] = []

for num in numbers{
if freqDict.keys.contains(num) {
freqDict[num] = freqDict[num]! + 1
} else {
freqDict[num] = 1
}
}

for (key, value) in freqDict where value >= 2 {
newArray.append(key)
}

print(newArray)
```

4. **Given a String, find the second most frequently occurring letter in a string**

Input: `Never trust a computer you can't throw out a window ~ Steve Wozniak`

Output `o`

```
var myString = "Never trust a computer you can't throw out a window ~ Steve Wozniak"
var freqDict = [Character: Int]()
var count:Int = 0

for c in myString where c != " "{
if freqDict.keys.contains(c) {
freqDict[c] = freqDict[c]! + 1
} else {
freqDict[c] = 1
}
}

var secondMostCommon = (freqDict.sorted(by: {$0.value > $1.value})[1])
print(secondMostCommon.key)
```


## Closures

1. **Given an array of type [String], return an array that contains the Strings sorted alphabetically with capital letters first (Swift will do that part automatically)**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["Never", "a", "a", "can\'t", "computer", "out", "throw", "trust", "window", "you"]`

```
var words = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]
let capitalWords = words.sorted {$0 < $1}
print(capitalWords)
```

2. **Given an array of type [String], return an array that contains the Strings sorted by length**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["a", "a", "you", "out", "Never", "trust", "can\'t", "throw", "window", "computer"]`

```
var words = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]
let wordsSortedByLength = words.sorted {$0.count < $1.count}
print(wordsSortedByLength)
```

3. **Given an array of type [String], return an array containing all Strings at least 4 characters long**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["Never", "trust", "computer", "can\'t", "throw", "window"]`

```
var words = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a",[ "window"]


let longWords = words.filter { (word) -> Bool in
return word.count >= 4
}
```

4. **Given an array of type [String], return a String containing all of the Strings from the array combined and separated by spaces.  Do this first without using the `joined(separator:) method`**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `Never trust a computer you can't throw out a window`

```
var input = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]

var newString2 = input.reduce("", {a, b in
a + b + " "
})
print(newString2)
```


## Enums


1. **Given an array of type [Int] and an instance of NumberType (defined below), return an array containing only all the even or odd numbers.**

```swift
enum NumberType {
    case even
    case odd
}
```
```
let number = [1,2,3,4,5,6]
enum NumberType {

case even
case odd

func evenOrOdd(arr: [Int]) -> [Int] {
var numArr: [Int] = []
switch self {
case .even:
for numbers in arr where numbers % 2 == 0 {
numArr.append(numbers)
}

case .odd:
for numbers in arr where numbers % 2 != 0 {
numArr.append(numbers)
}
}
return numArr
}
}

let even = NumberType.even
let odd = NumberType.odd

print(even.evenOrOdd(arr: number))
```
Input: `[1,2,3,4,5,6], NumberType.odd`

Output: `[1,3,5]`

2. **Given a String and an instance of StringType (defined below), return the String either lowercased or uppercased**

```swift
enum StringType {
    case lowercase
    case uppercase
}
```

Input: `"Design is not just what it looks like and feels like. Design is how it works", .uppercase`

Output: ``"DESIGN IS NOT JUST WHAT IT LOOKS LIKE AND FEELS LIKE. DESIGN IS HOW IT WORKS"``

```
enum StringType {
case lowercase
case uppercase

func stringTransformer(str: String) -> String {
var newStr: String = ""
switch self {
case .lowercase:
newStr = str.lowercased()
case .uppercase:
newStr = str.uppercased()
}
return newStr
}
}
let uppercase = StringType.uppercase
let lowercase = StringType.lowercase

print(uppercase.stringTransformer(str: "Design is not just what it looks like and feels like. Design is how it works"))
```

3. **Given an array of type [FileStatus] (defined below) and an Int, return an array containing only files that were saved more than that many times**

```swift
enum FileStatus: CustomStringConvertible {
    case unsaved
    case saved(numberOfVersions: Int)
    var description: String {
        switch self {
        case .unsaved: return "Unsaved File"
        case let .saved(numberOfVersions): return "File that has been saved \(numberOfVersions) times"
        }
    }
}
```

Input: `[FileStatus.saved(numberOfVersions: 5), FileStatus.saved(numberOfVersions: 3), FileStatus.saved(numberOfVersions: 8)], 4`

Output: `[File that has been saved 5 times, File that has been saved 8 times]`
