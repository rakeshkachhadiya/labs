import UIKit

/***** Swift Functions *****/

func sayHello() {
    print("Hello")
}

sayHello()

func printFullName(name: String, surname: String) -> String {
    return("Name is \(name) and Surname is \(surname)")
}

var fullname = printFullName("Adam", surname: "Smith")
print(fullname)

// External Parameter name

func printMessage(message message:String){
    print("Message is \(message)")
}

printMessage(message: "A Sample Message")

// Default Function Parameters

func printMessage(name name:String , surname:String = "Smith"){
    print("Name is \(name) and Surname is \(surname)")
}

printMessage(name: "Sam")
printMessage(name: "Sam", surname: "Nathan")

// Functions returning multiple values using tuple

func calculate(number:Int) -> (square:Int,cube:Int){
    let square = number * number
    let cube = number * number * number
    return (square,cube)
}

var digit:Int = 10
var answer = calculate(digit)
print("\(digit) square is \(answer.square)")
print("\(digit) cube is \(answer.cube)")

// Functions accepting variable number of parameters

func magic(numbers:Int...) -> Int {
    var temp = 0
    for num in numbers {
        temp+=num
    }
    return temp
}

magic(1)
magic(1,2)
magic(1,2,3)

// Passing values by reference

func swapper(inout a:Int , inout b:Int){
    let temp = a;
    a=b;
    b=temp
}

var a = 10
var b = 20
swapper(&a, b: &b)
print("a is \(a) and b is \(b)")

// Function Types as Return Types

func stepForward(input: Int) -> Int {
    return input + 1
}

func stepBackward(input: Int) -> Int {
    return input - 1
}

func chooseStepFunction(backwards: Bool) -> ((Int) -> Int) {
    return backwards ? stepBackward : stepForward
}


/***** Swift Closures *****/

// Closure Expressions

var names = ["Chris", "Alex", "Ewa", "Barry", "Daniella"]

names.sortInPlace { (str1: String, str2: String) -> Bool in
    return Int(str1) < Int(str2)
}

names

let printHello = { print("Hello") }
printHello()

let multiply = {(val1: Int, val2: Int) -> Int in
    return val1 * val2
}
let result = multiply(10, 20)

// a simple function that doubles an int
func doubler(i: Int) -> Int { return i * 2 }

func prefixSalutations(names:[String], completion:(namesWithSalutations:[String])->()){
    var salutations:[String] = []
    for name in names {
        salutations.append("MR "+name)
    }
    completion(namesWithSalutations: salutations)
}

prefixSalutations(["Vipul","Vinay","Vishal"], completion: { (namesWithSalutations:[String]) -> () in
    for name in namesWithSalutations {
        print(name)
    }
})


/***** Swift Classes *****/

class BankAccount {
    
    // Stored Properties
    var accountBalance: Float = 0
    var accountNumber: Int = 0
    
    // Computed Properties
    var interest : Float {
        get {
            return (10 * self.accountBalance)/100
        }
    }
    
    // initializer
    init(accountBalance:Float,accountNumber:Int){
        self.accountBalance=accountBalance
        self.accountNumber=accountNumber
    }
    
    // Instance Method
    func displayBalance() {
        print("Number \(accountNumber)")
        print("Current balance is \(accountBalance)")
    }
    
    // Class Method
    class func getMaxBalance() -> Float {
        return 10000
    }
    
    // de-initializer
    deinit {
        self.accountBalance = 0
        self.accountNumber = 0
    }
}

var bankAccount:BankAccount = BankAccount(accountBalance: 30, accountNumber: 11111)
bankAccount.displayBalance()
bankAccount.interest


/***** Swift Inheritance *****/

class SavingsAccount : BankAccount {
    var interestRate : Float
    
    init(accountBalance: Float, accountNumber: Int, interestRate: Float) {
        self.interestRate = interestRate
        super.init(accountBalance: accountBalance, accountNumber: accountNumber)
    }
    
    func calculateInterest() -> Float {
        return interestRate * accountBalance
    }
}

var savingsAccount : SavingsAccount = SavingsAccount(accountBalance: 10, accountNumber: 1111, interestRate: 10)
print(savingsAccount.calculateInterest())
savingsAccount.displayBalance()


/***** Swift Collections *****/

// Mutable Array
var countries : [String] = ["India","USA","U.K"]

// Empty Array
var cities = [String]()

// Empty Array with Capacity and default values
var languages = [String](count: 10, repeatedValue: "Swift")

print(countries.count)
print(cities.isEmpty)

// Array Operations
cities.append("Mumbai")
cities += ["Phoenix"]
cities.append("London")
cities.insert("Paris", atIndex: 1)
cities.removeAtIndex(1)
cities.removeLast()
cities.removeAll(keepCapacity: true)

// Mutable Dictionary
var empDict:[String:String] = ["Alan":"2000$","Pete":"4000$","Chris":"5000$"]
print(empDict["Alan"])

if let salary = empDict["Alan"] {
    print(salary)
}

// Iterating over dictionary
for (name,salary) in empDict {
    print("\(name) earns \(salary)")
}

// Dictionary Operations
empDict.removeValueForKey("Alan")
empDict.updateValue("$8000", forKey: "Pete")
empDict

// Set Use to hold unique values

var employees : Set = ["Akshay","Anil","Amit","Anvay"]
employees.count
employees.insert("Vipul")
employees.remove("Vipul")

if employees.contains("Akshay") {
    print("He is there!!")
}
else{
    print("He is not there!!")
}

for employee in employees {
    print(employee)
}

employees.sort { (str1: String, str2: String) -> Bool in
    return Int(str1) < Int(str2)
}

print(employees)

// Generics  Used for handling multiple data types

func swapValues<T>(inout item1:T,inout item2:T){
    let temp = item1
    item1 = item2
    item2 = temp
}

var n1 = 10
var n2 = 20
swapValues(&n1, item2: &n2)
print("\(n1) and \(n2)")

var str1 = "Vipul"
var str2 = "Vinay"
swapValues(&str1, item2: &str2)
print("\(str1) and \(str2)")

class MagicalClass<T> {
    var value:T
    
    init(value:T){
        self.value=value
    }
    
    func printValue(){
        print("Value is \(value)")
    }
}

var m1 : MagicalClass = MagicalClass(value: 10)
m1.printValue()

var m2 : MagicalClass = MagicalClass(value: "Vipul")
m2.printValue()


/***** Swift Protocols *****/

protocol RandomNumberGenerator {
    func random() -> Double
}

class Sample: RandomNumberGenerator {
    var lastRandom = 42.0
    let m = 139968.0
    let a = 3877.0
    let c = 29573.0
    
    func random() -> Double {
        lastRandom = ((lastRandom * a + c) % m)
        return lastRandom / m
    }
}

let sample :Sample = Sample()
sample.random()

/***** Swift Extensions *****/

extension String {
    var uppercase: String { return self.uppercaseString }
}

var sampleName = "Edureka"
sampleName.uppercase

extension Array {
    var top: Element { return self[0] }
    var second: Element { return self[1] }
    var bottom: Element { let last = self.count - 1; return self[last] }
}

var things = [1, 2, 3, 4, 5]

things.top
things.second
things.bottom


/***** Swift Subscripts *****/

extension String {
    subscript(pattern: String) -> String? {
        get {
            let range = self.rangeOfString(pattern)
            
            if range!.isEmpty {
                return nil
            } else {
                return pattern
            }
        }
        
        set(replacement) {
            let range = self.rangeOfString(pattern)
            
            if !(range!.isEmpty) {
                self = self.stringByReplacingCharactersInRange(range!, withString: replacement!)
            }
        }
    }
}

var message = "This is an awesome message"
print(message["awesome"])

message["awesome"] = "beautiful"
print("Message is \(message)")


class DailyMeal
{
    enum MealTime
    {
        case Breakfast
        case Lunch
        case Dinner
    }
    
    var meals: [MealTime : String] = [:]
    
    subscript(requestedMeal: MealTime) -> String?
        {
        get
        {
            return meals[requestedMeal]
        }
        set(newMealName)
        {
            meals[requestedMeal] = newMealName
        }
    }
}

var monday = DailyMeal()

monday.meals[.Breakfast] = "Toast"

if let someMeal = monday.meals[.Breakfast]
{
    print(someMeal)
}
