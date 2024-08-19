# Enums

* Enumerations allow you to group related values together

* Every enumeration has a descriptive name, and the body contains the associated values for that enumeration.

```
enum EnumName {
   case value1 
   case value2 
   case value3
}
```

## Creating an enumeration

```
enum TrafficLightColor {
   case red 
   case yellow 
   case green
   
   func description() -> String {
      switch self {
      case .red:
         return "red" 
      case .yellow:
         return "yellow" 
      default:
         return "green"
      }
   }
}

var trafficLightColor = TrafficLightColor.red
print(trafficLightColor.description())

```

* just like classes and structures, enumerations can contain methods. 

