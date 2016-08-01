# How Hot Is My Coffee? Sensors, Core Bluetooth and Swift!
_Evan K. Stone (from [CloudCity Development](http://www.cloudcity.io/))_

* [IoT test device](https://store.ti.com/cc2650stk.aspx). Perfect for testing different types of peripherals
* Sensors (peripherals) becomes an extension of our iOS device, giving it abilities it didn't have previously
* 4 main players: central, peripheral, service, characteristic
* Feels very client-server like
* Advertising and discovery - devices finding peripherals (and vice versa) "Kinda like a headhunter on LinkedIn" ಠ_ಠ

# Accessing Sensor Data on Apple Watch & Apple TV
_[Ethan Fan](https://github.com/coolioxlr)_

* watchOS 2 sucked. Lots of false promises like being able to use sensors, but only when the screen is turned on. Whhaa?!
* watchOS 3
  - Workout access (enable it once, full access to sensors)
  - Gyroscope access
  - Recorder access up to 36 hours, 3 seconds to retrieve
* Workout use cases
  - Attitude - rep counting - weight training
  - Gravity - tracking poses - yoga
  - Rotation rate - speed of circular motion - bat speed
  - User acceleration - change in linear motion - punch/recoil
* Heart rate streaming
  1. Request HealthKit auth for hear rate
  2. Start `HKWorkoutSessions`
  3. Query HealthKit for new heart rate (updates every 5 seconds)
* tvOS remote has an accelerometer and gyroscope that can be used to track motion (primarily for games, but also could be used for fitness)
* Core Bluetooth
  - Apple's abstraction for Bluetooth (and BLE)
  - iOS Simulator does not support BLE (need to use an actual device - iPhone 4s and later, iPad 3 and later)

# Inferences and Generics
_[Richard Fox](https://twitter.com/rgfox)_

* **Generics**: Way of programming to an unknown type
* **Inference**: Figuring out what those unknown generics are based on how it's being used
* New in Swift 3 generics: Generic typealias
* Lots of code examples. Slides have specifics.

<sup>[Slides](https://www.dropbox.com/s/vycmo4lutpkmc5p/FinishedPresentation.pdf?dl=0)</sup>

# Discovering Native Swift Patterns
_[Nick O'Neill](https://twitter.com/nickoneill)_

# Cross-platform Swift
_Boris Bügling_

# ObjC<->Swift Interoperability and The Future
_Nikita Lutsenko_

# Closing ePlenary
_[Erica Sadun](http://ericasadun.com/)_
