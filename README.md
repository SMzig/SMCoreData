# SMCoreData

## Installation

### Cocoapods

SMCoreData is available through [CocoaPods](https://cocoapods.org). To install
it, simply add the following line to your Podfile:

```ruby
pod 'SMCoreData'
```

### Swift Package Manager

1. File > Swift Packages > Add Package Dependency
2. Add `https://github.com/SMzig/SMCoreData.git`

_OR_

Update `dependencies` in `Package.swift`
```swift
dependencies: [
    .package(url: "https://github.com/SMzig/SMCoreData.git", .upToNextMajor(from: "1.0.0"))
]
```

## Usage
Insert data
```swift
try SMDBHelper.shared.insertInto(entity: "TableUser", parameter: ["name":"sudhir", age: 10])
```

Fetch data
```swift
let arrResult = try SMDBHelper.shared.fetch(entity: "TableUser") as? [User]
```

Update data
```swift
let predicate = NSPredicate(format: "name==%@", argumentArray: ["YOUR_NAME"])

let arrResult = try SMDBHelper.shared.update(entity: "TableUser", predicate: predicate, parameter: ["name":"sudhir", age: 10])
```

Delete data
```swift
try SMDBHelper.shared.delete(entity: "TableUser", predicate: NSPredicate(format: "name==%@", argumentArray: ["YOUR_NAME"]))
```
