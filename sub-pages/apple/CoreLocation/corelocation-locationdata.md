# Core Location - Location Data



1. Import CoreLocation
2. Ask for permission & request for Location
3. Edit Info.plist
4. Implement delegates methods (didUpdateLocations didFailWithError)



## Import CoreLocation

```
import CoreLocation

// somewhere in class 

let locationManager = CLLocationManager()
```


## Ask for permission & request for Location

```
// in viewDidLoad()

override func viewDidLoad(){
    super.viewDidLoad()
    ...
    // -- ask for permission
    locationManager.delegate = self
    locationManager.requestWhenInUseAuthorization()
    locationManager.requestLocation()
    ...
}

```

## Edit Info.plist

```
// in Information Property List add:

Privacy - Location When In Use Usage Description

// Add value, e.g.: 
"We need your location to get current weather for where you are." 

```

## Implement delegates method

```
func locationManager(_ manager: CLLocationManager, didUpdateLocations locations: [CLLocation] ){
    if let location = locations.last{
        locationManager.stopUpdatingLocation()
        let lat = location.coordinate.latitude
        let lon = location.coordinate.longitude
        print(lat)
        print(lon)
    }
}


func locationManager(_ manager: CLLocationManager, didFailWithError error: Error ){

}
```