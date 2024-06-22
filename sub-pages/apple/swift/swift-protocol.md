# Swift Protocol

## Class and Protocols
* if class needs to inherit from super class ... this comes first
* protocols after inheritance

```
class MyClass: Superclass, FirstProtocol, SecondProtocol{
    // class definition goes here
}
```


```
protocol CanFly {
    func fly()
}

class Bird {
    var isFemale = true
    
    func layEgg(){
        if isFemale{
            print("The bird makes a new bird in a shell.")
        }
    }
    
   // func fly(){
   //     print("The bird flaps its wings and lifts off into the sky.")
   // }
    
}

class Eagle: Bird, CanFly {
    func soar(){
        print("The eagle glides in the air using air currents.")
    }
    
    func fly(){
        print("The bird flaps its wings and lifts off into the sky.")
    }
}

class Penguin: Bird{
    func swim(){
        print("The penguin paddles through the water.")
    }
}

struct FlyingMusem {
    func flyingDemo(flyingObject: CanFly){
        flyingObject.fly()
    }
}

struct Airplane: CanFly{
    func fly() {
        print("The airplane uses its engine to lift off into the air.")
    }
}

let myEagle = Eagle()
myEagle.fly()
myEagle.layEgg()

let myPenguin = Penguin()
// myPenguin.fly() // penguin do not fly - use protocol

let museum = FlyingMusem()
//museum.flyingDemo(flyingObject: myPenguin) // penguin do not fly - use protocol

let myAirpalne = Airplane()
museum.flyingDemo(flyingObject: myAirpalne)


```






# Delegate Pattern
* uses protocol
// The Delegate Patern

```
protocol AdvanceLifeSupport{
    func performCPR()
}


class EmergencyCallHandler{
    var delegate: AdvanceLifeSupport?
    
    func assessSituation(){
        print("Can you tell me what happened?")
    }
    
    func medicalEmergency(){
        delegate?.performCPR()
    }
}


struct Paramedic: AdvanceLifeSupport{
    
    init(handler: EmergencyCallHandler){
        handler.delegate = self
    }
    
    func performCPR() {
        print("The paramedic does chest compressions, 30 per seconds!")
    }
    
    
}

class Doctor: AdvanceLifeSupport {
    init(handler: EmergencyCallHandler) {
        handler.delegate = self
    }
    func performCPR() {
        print("The paramedic does chest compressions, 30 per seconds!")
    }
    
    func useStethoscope(){
        print("Listening for heart sounds")
    }
    
}


class Surgeon: Doctor{
    override func performCPR() {
        super.performCPR()
        print("Sings staying alive by the BeeGees")
    }
}

let emilio = EmergencyCallHandler()
let pete = Paramedic(handler: emilio)
let angela = Surgeon(handler: emilio)

emilio.assessSituation()
emilio.medicalEmergency()



```


Note: Swift Documentation