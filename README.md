# Swift Basic
```swift
import UIKit

//var str = "Hello, playground"
//Semiclones no need

/*
 Comment Area
 
 */

var helloWorld: String = "Hello World"
helloWorld += " from Xcode"

let helloConstant: String = "This is a String"
//helloConstant = "New Value" //Error

var mutableString = "Swift"
print(type(of: mutableString))

//String Interpolation
print("\(mutableString) is a Type Safe Language")

let 🐱 = "🐶🐶🐶🐶🐶🐶🐶🐶🐶🐶"
print(🐱)
//String Comparison
let ab = "inital value"
let xy = "Final Value"
print(ab == xy)

//String Concatenation
let result = ab+xy


result.isEmpty
result.count
result.hasPrefix("inital")

//Int Double Float

var mutableInt: Int = 1
mutableInt = 2

let double: Double = 2.0
let float: Float = 2.0

var dubleVariable = 2.0 // Inferred as a Duble

var x = 5, y = 10, z = 20

//Charecter

var thisisJ: Character = "J"
var banglaA: Character = "\u{0985}"
let random: Character = "\u{05465}"

//Bool
let score: Bool = false
if(score){
print("Empty")
}

//Tuples
let httpError = (503, "Server Error", "Database Missing")
print(httpError.0)

//Type Casting

let myString = "555"
let myInt = Int(myString)

let g = 4, h = 5.7
let i = g * Int(h)

// Operators
//Unary Operator
let latestScore = !score
//Binary Operator
let sum = 1 + 2

//Ternary Operator
let theResult = (50 > 10) ? "Value Larger" : "Value Smaller"

//Arithmetic Operators

let f = 10
let gg = 2
f+gg
f-gg
f*gg
f/gg

//Modulo Operator or Remainder
10%2

/*
 Comparison Operator
 ==
 !=
 >
 <
 >=
 <=

 
 Logical Operator
 
 &&
 
 !
 ||
 

 */

//Range Operator
let range = 0..<5

for i in range{
    print(i)
}

//Array
var mutableArray: [String] = ["Nabila", "Kabila"]
//let immutableArray: [String] = []

//Another Type of Array Declaration
//var song = [String]()
//var emptyArray = Array<String>()
//var secondArray: Array<String> = Array()
mutableArray.contains("Kabila")
//mutableArray[2] = "Sabila" // Error
mutableArray.append("Habila")
mutableArray.insert("Abila", at: 3)
mutableArray.remove(at: 3) // Abila

mutableArray.append(contentsOf: ["Shakia","William"])

var numbers: [Int] = []
numbers.append(contentsOf: stride(from: 2000, to: 2100, by: 10))

numbers.count
numbers.first
numbers.last
numbers.isEmpty
numbers.randomElement()

numbers.forEach{
    print($0)
}

for num in numbers{
    print(num)
}

//Dictionary

var emptyDict: [String:String] = [:]
var mutableDict: [String:String] = ["Student1": "Sakib", "Student2": "Musfiq"]
mutableDict["Student1"]
//mutableDict.removeValue(forKey: "Student2") // Musfiq

for (key,value) in mutableDict{
    print("\(key) name is \(value) ")
}

//Set
let emptySet: Set = [1]
print(emptySet)

let setA: Set = [5, 10, 21, 5]
let setB: Set = [30, 40, 5]
for setValue in setA{
    print(setValue)
}
// Union
print(setA.union(setB))
print(setA.intersection(setB))
print(setA.subtracting(setB))
print(setA.symmetricDifference(setB))

//Loops
//for item in collection {
//    print(item)
//}

for ii in 0..<5{
    print(ii)
}

let names = ["Ana", "Alex", "Brain", "Jack"]
for body in names{
    print("Hello \(body)")
}

var ht = 0
while ht<10 {
    ht += 1
    print(ht)
}

repeat{
    ht -= 1
    print(ht)
}while(ht>0)

//Conditional Statement

//if expression{
//    //statement
//}
let nu = 0
if nu>0{
    print("This is a Positive Number")
}else if (nu < 0){
    print("The Number is Negative")
}else{
    print("Number is zero")
}


//guard condition else{
//    statement
//    continue
//    break
//    throw
//    return
//}

for n in 1...30{
    guard n%2 == 0 else {
        print("\(n) is odd")

        continue
    }
    print("\(n) is even")
}


let year = 2012

switch year{
case 2003, 2004:
    print("Panter or Tiger")
case 2010:
    print("Lion")
case 2012...2015:
    print("Mountain Lion, EL Captain")
default:
    print("Not Clasified")
}

//Function

func writeYourName(name: String){
    print("This is my name: \(name)")
}

writeYourName(name: "Maruf")
writeYourName(name: "Ana")

func greet(person: String, alreadyGreeted: Bool)->String{
    if alreadyGreeted == true{
        let greetings = "Hello, "+person+"! again."
        return greetings
    }else{
        let greetings = "Hello, "+person+"!"
        return greetings
    }
    
    
}
greet(person: "Bob", alreadyGreeted: true)

func minMax(array: [Int]) -> (Min: Int, Max: Int){
    var currentMin = array[0]
    var currentMax = array[0]
    for value in array[1..<array.count]{
        if value < currentMin{
            currentMin = value
        }else if value > currentMax{
            currentMax = value
        }
    }
    return (currentMin, currentMax)
}

let mm = minMax(array: [3, 5, 8, 14, 98, 21])
print(mm.Min)
print(mm.Max)

//Specifying Argument Name/Label

func someFunc(person: String, _ hometown: String)->String{
    return "Hello \(person), Glad you could visit from \(hometown)."
}

someFunc(person: "Salman", "Dhaka")

//Default Parameter sokale suro korbo
func writeYourNames(name: String = "Maruf"){
    print("This is my name: \(name)")
}

// Default Parameter
func language( lang: String = "English"){
    print("Selected Language is: \(lang)")
}

language()

//Veriadic Parameters (...)
func arithmeticMean(_ numbers: Double...)-> Double {
    var total: Double = 0.0
    for number in numbers{
        total += number
    }
    return total/Double(numbers.count)
}

let am = arithmeticMean(1.0, 3.0, 5.6, 7.9, 8.0)
print(am)
// Nested Function,

func outputMes(_ message: String){
    
    func greetingsMes(){
        print("Sir, \(message)")
    }
    greetingsMes()
}

outputMes("This is my message!")

//Recursive

func countDownToZero(num: Int){
    print(num)
    if num > 0 {
        countDownToZero(num: num-1)
    }
}
countDownToZero(num: 25)

// in out paramter _:

func swapInt(_ a: inout Int,_ b: inout Int){
let temA = a
    a = b
    b = temA
}
var xc = 12
var yc = 18
swapInt(&xc, &yc)
print(xc)
print(yc)


// Closure

func myFunction(number: Int)->Int {
    let result = 6 * number
    return result
}

let myClosure = {(number: Int)->Int in
    let result = 3 * number
    return result
}
let myClosure1:(_ number: Int)->Int = {(number: Int)->Int in
    let result = 3 * number
    return result
}
let myClosure2: (Int)->Int = {(number: Int)->Int in
    let result = 3 * number
    return result
}

let myClosure3 = {(number: Int) in 3 * number}

let myClosure4 = {3 * $0}
   // { in }
let unit = 5

myFunction(number: {(number: Int)->Int in
    let result = 3 * number
    return result
}(unit))

//myClosure(12)
//myClosure1(12)
//myClosure2(12)
//
//myClosure3(12)
//
//myClosure4(12)

let earnMarks = 27

func findGrade(marks: Int)->String{
    var Status: String
    print(marks)
    if marks < 33 {
        Status = "Failed"
    }else if marks >= 33 && marks <= 60 {
        Status = "Average"
    }else{
        Status = "Super"
    }
    return Status
}

let grace = {(marks: Int) -> Int in
    return marks >= 33 ? marks : marks+5
    // conditon ? True : False
}

findGrade(marks: {(marks: Int) -> Int in
    return marks >= 33 ? marks : marks+5
}(earnMarks))

findGrade(marks: earnMarks)

// Enumerations or Enum


enum CompassPoint{
    case north
    case south
    case east
    case west
}

enum Planet{
    case mercury, venus, earth, mars
}


var direction = CompassPoint.west
direction = .east

switch direction {
case .north:
    print("Lots of planets have a north")
case .south:
    print("Watch out for penguins")
case .east:
    print("WHERE THE SUN RISES")
case .west:
    print("Where the skies are blue")

}


enum Beverage: CaseIterable {
    case coffie, tea, juice
}
let numberOfChoice = Beverage.allCases.count
print((numberOfChoice))

for items in Beverage.allCases {
    print(items)
}

//rawValue
enum MyColor: String {
    case white = "#ffffff"
    case black = "#000000"
    
}

let whiteColor = MyColor.white.rawValue

// Associate value

enum CustomColor{
    case ccolor(hex: String)
}

let ourCustomColor = CustomColor.ccolor(hex: "#000000")

struct Person{
    var clothes: String
    func Description() {
        print("your clothes is \(clothes)")
    }
}

// Stuctures

struct Personal {
    var clothes: String
    var shoes: String
    
    func  Description() {
        print("Nice \(clothes) and \(shoes)")
    }
    
}

let sakib = Personal(clothes: "T-Shirt", shoes: "Sneakers")
print(sakib.clothes)
print(sakib.shoes)

sakib.Description()

// Classes
//Object || Instance

//let bob = Body(cloth: "T-Shirt")
//bob.clothes
////  refference type vs value type
//var kavin = bob
//kavin.clothes = "Polo Shirt"
//
//bob.clothes
//kavin.clothes
//
//// Static Propertise and method
//Body.sayHello()
//Body.dressfor = "Animal"
//Body.dressfor

class Body {
    //Store Propertise //var age = 50
    var age: Int { return 50}
    // Static Propertise
    static var dressfor = "Humna"
    // Propertise
    var clothes : String
    // Initialization
    init(cloth: String){
        self.clothes = cloth
    }
    //Method
    func wearDress(){
        print(" I wear nice \(clothes)")
    }
    //Static Method
    static func sayHello(){
        print("I dressed well")
    }
}

// Inheritance // Sub Class : Super Class
class Bangalee : Body {
    override var age: Int {return 40}
    var salute: String = "Md."
    var shoes: String
    init(cloth: String, shoes: String){
        self.shoes = shoes
        super.init(cloth: cloth + "our traditional dress")
    }
    func greetings(){
        print("Good Morning")
    }
    override func wearDress(){
        print(" I wear nice bangalee dress, say \(clothes), its 100% cotton")
    }
}
// Sub Class
Bangalee.dressfor
Bangalee.sayHello()
// Object of Bangalee
let mokless = Bangalee(cloth: "Paja Panjabi", shoes: "Sandle")
mokless.clothes = "Shirt & Lungi"
mokless.shoes
mokless.wearDress()
mokless.age
mokless.salute
mokless.greetings()

```