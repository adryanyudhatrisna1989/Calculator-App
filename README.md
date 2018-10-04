# Calculator-App with iOS 12 and Swift 4.2

### Calculator Image
<a href="https://imgflip.com/gif/2jckv9"><img src="https://i.imgflip.com/2jckv9.gif" title="made at imgflip.com"/></a>

### Code Example
```Swift
struct CalculatorLogic {
    
    private var number: Double?
    
    var intermediateCalculation: (n1: Double, calcMethod: String)?
    
    mutating func setNumber(_ number: Double) {
        self.number = number
    }
    
    mutating func calculate(symbol: String) -> Double? {
        
        if let n = number {
            switch symbol {
            case "+/-":
                return n * -1
            case "AC":
                return 0
            case "%":
                return n * 0.01
            case "=":
                return performTwoNumCalculation(n2: n)
            default:
                intermediateCalculation = (n1: n, calcMethod: symbol)
            }
        }
        return nil
        
    }
