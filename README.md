# Optionals lab

Fork and clone this repo. On your fork, answer and commit the follow questions. When you are finished, submit the link to your repo on Canvas.


## Question 1

`var userName: String?`

Write 3 different ways of safely unwrapping and printing the value of `userName`.  If it is nil, print "No name".

- Method one: Check for nil and force unwrap

- Method two: Optional binding

- Method three: Nil coalescing

```
swift
//Q1

var userName: String?

//Q1 Method 1
if userName != nil{
print(userName!)
}

//Q2 Method 2
if let name = userName{
print("\(name)")
}

//Q3 Solution 1
let someName = userName ?? "Anonymous"
print(someName)

//Q3 Solution 2
print("\(userName ?? "Anonymous")")
```


## Question 2

Given optional string `backgroundColor`, write code that safely unwraps and prints it. If backgroundColor is nil, give it a value.

`var backgroundColor: String?`

```
swift
//Q2
var backgroundColor: String?

print("\(backgroundColor ?? "No Color")")
```


## Question 3

Given an optional width and an optional height of a rectangle, write code that calculates and prints the area. Print an error message if either value is nil.

```swift
var width: Double?
var height: Double?
```
```
swift
//Q3
var width: Double?
var height: Double?

if let w = width, let h = height{
print(w*h)
}else{
print("Error: One or more dimensional doesn't exist")
}

```


## Question 4

Given the following optional variables `name`, `age` and `height`. Write code so that it prints `name`, `age` and `height` if they all have a value. If any are nil, print an error message. Try using optional binding.

```swift
var name: String?
var age: Int?
var height: Double?
```
```
swift
//Q4
var name: String?
var age: Int?
var height: Double?

if let n = name, let a = age, let h = height{
    print("\(n), \(a), \(h)")
    }else{
        print("Missing Attribute")
}

```


## Question 5

Given the variables `firstName`, `middleName` and `lastName`. Create a variable called `fullName` that is a nicely formatted string.

```swift
var firstName: String = "Johnny"
var middleName: String?
var lastName: String = "Stone"
```
```
swift
//Q5
var firstName: String = "Johnny"
var middleName: String?
var lastName: String = "Stone"

var fullName = String()

if let m = middleName{
    fullName = "\(firstName) \(m) \(lastName)"
}else{
    fullName = "\(firstName) \(lastName)"
}

print(fullName)
```


## Question 6

Write code that adds 15 to `myIntString`, then prints the sum. Use the `Int()` constructor which returns an optional Int `(Int?)`.

`let myIntString = "35"`
```
swift
//Q6

let myIntString = "35"
var answer: Int? = ((Int)(myIntString) ?? 0 ) + 15

```


## Question 7

Given an optional tuple of optional Ints, write code to safely unwrap the tuple and calculate the sum of its contents that aren't nil.

```swift
var scores: (Int?, Int?, Int?)?

var testCaseOne = (4, nil, 7)
var testCaseTwo = (nil, nil, 9)
var testCaseThree = (5, 10, 24)
```
```
swift
//Q7 
var testCaseOne: (Int?, Int?, Int?)? = (4, nil, 7)
var testCaseTwo: (Int?, Int?, Int?)? = (nil, nil, 9)
var testCaseThree: (Int?, Int?, Int?)? = (5, 10, 24)

var sum = 0

func addition(scores: (Int?, Int?, Int?)?)->(){
if let score = scores{

    if let s0 = score.0{
        sum += s0
    }
    if let s1 = score.1{
        sum += s1
    }
    if let s2 = score.2{
        sum += s2
    }
}
print(sum)
}

addition(scores: testCaseOne)


```



## Question 8

Safely unwrap `tuple` if there’s a non-nil tuple value and print it out.

```swift
var tuple: (Int, Int)?
if Bool.random() {
 tuple = (5, 3)
}
```
```
swift
//Q8
var tuple: (Int, Int)?
    if Bool.random() {
        tuple = (5, 3)
}

if let t = tuple{
    print(t)
}
```


## Question 9

Write code that either doubles `myInt` and then prints it, or prints an error message if myInt is nil.

```swift
var myInt: Int?
if Bool.random() {
 myInt = 5
}
```
```
swift
//Q9
var myInt: Int?
if Bool.random() {
myInt = 5
}

if let m = myInt{
    print(2*m)
}else{
    print("Error")
}
```


## Question 10

Write code that prints out the product of `myDouble` and `doubleTwo` or prints an error message if `myDouble` is nil.

```swift
var myDouble: Double?
let doubleTwo: Double = 5

if Bool.random() {
    myDouble = 12
}

```

```swift
//Q10
var myDouble: Double?
let doubleTwo: Double = 5

if Bool.random() {
myDouble = 12
}

//Solution
if let m = myDouble{
print(m*doubleTwo)
}else{
print("Error!")
}
```


## Question 11

Determine if the variable contains a Boolean or nil value. If nil set the variable to false, else keep it true.

```swift
var isTheGreatest: Bool?

if Bool.random() {
 isTheGreatest = true
}
```
```
swift
//Q11
var isTheGreatest: Bool?

if Bool.random() {
    isTheGreatest = true
}

print(isTheGreatest ?? false)
```


## Question 12

Given the code below print the sum of each non-nil element in `myTuple`.

 ```swift
var myTuple: (Int?, Int?, Int?, Int?)

if Bool.random() {
 myTuple.0 = 5
 myTuple.2 = 14
} else {
 myTuple.1 = 9
 myTuple.3 = 10
}
```
```
swift
//Q12
var myTuple: (Int?, Int?, Int?, Int?)
var sum = 0

if Bool.random() {
    myTuple.0 = 5
    myTuple.2 = 14
    } else {
    myTuple.1 = 9
    myTuple.3 = 10
}

if let t0 = myTuple.0{
    sum += t0
}
if let t1 = myTuple.1{
    sum += t1
}
if let t2 = myTuple.2{
    sum += t2
}
if let t3 = myTuple.3{
    sum += t3
}
print(sum)
```

## Question 13

Given the helper functions and code below, check to see if your `evolutionaryStone` is able to evolve your pokemon.  The table below shows the appropriate matches of pokemon to stone:

| Pokemon	   | Stone    |
| :--------: | :------: |
| Pikachu	   | Electric |
| Bulbasaur	 | Grass    |
| Charmander | Fire     |
| Squirtle	 | Water    |


```swift
// Helper Functions

func eStone() -> String {
 let random = Int(arc4random_uniform(5))
 switch random {
 case 0:
  return "Electric"
 case 1:
  return "Grass"
 case 2:
  return "Fire"
 case 3:
  return "Water"
 default:
  return "No Stone"
 }
}

func starterPokemon() -> String {
 let random = Int(arc4random_uniform(5))
 switch random {
 case 0:
  return "Pikachu"
 case 1:
  return "Bulbasaur"
 case 2:
  return "Charmander"
 case 3:
  return "Squirtle"
 default:
  return "Not a Pokemon"
 }
}

let pokemon: String?
var evolutionaryStone: String?
pokemon = starterPokemon()
evolutionaryStone = eStone()

//Solution
func evolution(pocketMonster: String?, stone: String? )->(){
    if let name = pocketMonster, let s = stone{
        switch name {
            case "Pikachu":
                if s == "Electric"{
                print("\(name) evolves into Raichu" )
                }else{
                print("\(name) didn't evolve" )
                }
            case "Bulbasaur":
                if s == "Grass"{
                print("\(name) evolves into Ivysaur?")
                print("FYI: \(name) doesn't evolve with any stone")
                }else{
                print("\(name) didn't evolve")
                }
            case "Charmander":
            if s == "Fire"{
                print("\(name) evolves into Charmeleon?")
                print("FYI: \(name) doesn't evolve with any stone")
            }else{
                print("\(name) didn't evolve")
            }
            case "Squirtle":
                if s == "Water"{
                    print("\(name) evolves into Warturtle?")
                    print("FYI: \(name) doesn't evolve with any stone")
                }else{
                        print("\(name) didn't evolve")
                }

            default:
                print("No such pokemon and/or stone exists")
                }
            }
}

evolution(pocketMonster: pokemon, stone: evolutionaryStone)

```


## Question 14

Given an optional int `numberOfPeople`, write code that unwraps and prints it **only if it is even**. Try using optional binding with a condition.

```swift
var numberOfPeople: Int?

if Bool.random() {
 numberOfPeople = 108
}
```
```
swift
//Q14
var numberOfPeople: Int?

if Bool.random() {
    numberOfPeople = 108
}

if let num = numberOfPeople{
    if num % 2 == 0{
        print(num)
    }
}
```


## Question 15

Given the array of optional Ints `someNumbers`, write code to find the product of the array not including any nil values.

```swift
var someNumbers: [Int?] = []

for i in 0..<20 {
    someNumbers.append(Bool.random() ? i : nil)
}
```
```
swift
//Q15

for i in 0..<10 {
someNumbers.append(Bool.random() ? i : nil)
}

//print(someNumbers)

for item in someNumbers{

    guard let i = item else{
    continue
}

    product *= i

}

print(product)

```


## Question 16

Given the array `poorlyFormattedCityNames`, create a new array with the city names capitalized and any nil values removed.

```swift
let poorlyFormattedCityNames: [String?] = ["new york", "BOSTON", nil, "chicago", nil, "los angeles", nil, "Dallas",]

Output: ["New York", "Boston", "Chicago", "Los Angeles", "Dallas"]
```
```
swift
//Q16

let poorlyFormattedCityNames: [String?] = ["new york", "BOSTON", nil, "chicago", nil, "los angeles", nil, "Dallas",]

var output: [String] = []

for cityName in poorlyFormattedCityNames{
    guard let name = cityName else{
    continue
    }

    output.append(name.uppercased())
}
print(output)
```


## Question 17

Given a random array of optional numbers, create a new array of all the even numbers that aren't nil.

```swift
var aBunchOfNumbers: [Int?] = []

for _ in 0..<20 {
 aBunchOfNumbers.append(Bool.random() ? Int(arc4random_uniform(102)) : nil)
}
```
```
swift
//Q17
var aBunchOfNumbers: [Int?] = []
var output: [Int] = []

for _ in 0..<20 {
aBunchOfNumbers.append(Bool.random() ? Int(arc4random_uniform(102)) : nil)
}

for item in aBunchOfNumbers{
guard let num = item else {
continue
}
if num % 2 == 0{
output.append(num)
}
}
print(output)

```

## Question 18

Given the following array of zip codes as strings, write code that turns them into an array of Ints.

`let zipCodeStrings = ["11377", "11101", "11373", "10014", "10003", "11223"]`

```
swift
//Q18
let zipCodeStrings = ["11377", "11101", "11373", "10014", "10003", "11223"]
var zipCodeIntegers: [Int] = []

for i in zipCodeStrings{
    if let num = Int(i){
    zipCodeIntegers.append(num)
    }
}
print(zipCodeIntegers)
```

## Question 19

Some students were asked some questions about their favorite foods and colors and the answers were stored in an array `studentInfo`.

- Print the names of the students that do not have a favorite color.

- Print the names of the students that don't have a favorite color or a favorite food.

- Create a new array of type `[(String, String, String)]` that contains the students with both favorite colors and foods.

`let studentInfo: [(String, String?, String?)] = [("Bill", "Burgers", "Blue"), ("Rita", nil, "Red"), ("Peter", "Pizza", "Purple"), ("Sarah", "Sandwiches", nil), ("Jeff", nil, nil), ("Lucy", "Leftovers", "Lilac"), ("Mike", "Meat", "Mauve"), ("Gemma", nil, "Green")]`

```
swift 
//Q19

let studentInfo: [(String, String?, String?)] = [("Bill", "Burgers", "Blue"), ("Rita", nil, "Red"), ("Peter", "Pizza", "Purple"), ("Sarah", "Sandwiches", nil), ("Jeff", nil, nil), ("Lucy", "Leftovers", "Lilac"), ("Mike", "Meat", "Mauve"), ("Gemma", nil, "Green")]

var both: [(String, String, String)] = []
//Print the names of the students that do not have a favorite color.
//
//- Print the names of the students that don't have a favorite color or a favorite food.
//
//- Create a new array of type `[(String, String, String)]` that contains the students with both favorite colors and foods.

for student in studentInfo{
if student.2 == nil{
print("\(student.0) does not have a favorite color")
}
}

for student in studentInfo{
if student.2 == nil{
print("\(student.0) does not have a favorite color")
}
if student.2 == nil && student.1 == nil{
print("\(student.0) does not have a favorite color or favorite food")
}
if let food = student.1 , let color = student.2{
both.append((student.0, food, color))
}
}
print(both)

```

## Question 20

Given an optional array of optional tuples of optional UInt8s,

- Write code to safely unwrap and print the tuples in the array with all 3 RGB values.

- Write code that counts all the nil values.

`let possibleColors: [(r: UInt8?, g: UInt8?, b: UInt8?)?]? = [(128, 21, 7), (0, 0, 0), nil, (nil, 25, 82), (255, 255, 255), nil, (200, 100, nil), (120, nil, 23), (0, 255, 106), (nil, nil, nil), nil, (100, 100, 200)]`

```
swift
//Q20

let possibleColors: [(r: UInt8?, g: UInt8?, b: UInt8?)?]? = [(128, 21, 7), (0, 0, 0), nil, (nil, 25, 82), (255, 255, 255), nil, (200, 100, nil), (120, nil, 23), (0, 255, 106), (nil, nil, nil), nil, (100, 100, 200)]

var nilCounter = 0

//Write code to safely unwrap and print the tuples in the array with all 3 RGB values.

if let pColors = possibleColors{

for color in pColors{
    if let r = color?.r, let g = color?.g, let b = color?.b{
        print((r,g,b))
    }else if color == nil{
        nilCounter += 1
}
    else{
        if color?.r == nil{
        nilCounter += 1
        }
        if color?.g == nil{
        nilCounter += 1
        }
        if color?.b == nil{
        nilCounter += 1
        }
    }
}
print("Number of Nils: \(nilCounter)")
}
```


## Question 21

Consider the following nested optional. It corresponds to a number inside a box inside a box inside a box.

- Fully force unwrap and print number.

- Optionally bind and print number.

`let number: Int??? = 10`

```
swift
//Q21
if let num = number{
    if let num1 = num{
        if let num2 = num1{
            print(num2)
        }
    }
}

```
## Question 22

Given an Array of Optional Strings, write code that concatenates all non-nil values together except for strings with 3 or more vowels.

`let monkeyingAround = ["orangutan", "apes",nil, "monkeys", "gorillas", "lemurs", nil]`

output: `"apesmonkeyslemurs"`

```
swift
//Q22

let monkeyingAround = ["orangutan", "apes",nil, "monkeys", "gorillas", "lemurs", nil]

var finalStr = String()

func moreThanThreeVowels(str:String)->(Bool){
  //let vowels = ["a","e","i","o","u"]
    let vowels = "aeiou"
    var counter = 0

    for c in str where vowels.contains(c){
        counter += 1
    }
    return (counter >= 3)
}

//moreThanThreeVowels(str: "Whatever")

for i in monkeyingAround{
    guard let i = i else{
        continue
}

if moreThanThreeVowels(str: i){
    continue
}
    finalStr += i
}

print(finalStr)

```


## Question 23

Given the value below, print out all of the non-nil Ints it contains by accessing each of them.

`var strangeStructure: ([Int]?, [[Int?]], [[Int]?], Int)? = ([1], [[2,3,4],[],[5,nil],[nil]], [nil, [6,7,8],nil,[],[9]], 10)`

```
swift
//Q23


var strangeStructure: ([Int]?, [[Int?]], [[Int]?], Int)? = ([1], [[2,3,4],[],[5,nil],[nil]], [nil, [6,7,8],nil,[],[9]], 10)

if let strangeStruct = strangeStructure{

if let s0 = strangeStruct.0{
    print(s0)
}
for i in strangeStruct.1{
    for j in i{
        if let k = j{
            print(k)
        }
    }
}
for a in strangeStruct.2{
    if let a1 = a {
        for b in a1{
            if b != nil{
                print(b)
            }
        }
    }
}

if strangeStruct.3 != nil{
    print(strangeStruct.3)
    }
}
```
