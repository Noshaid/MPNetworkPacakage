# MPNetworkPackage

## Overview

**MPNetworkPackage** is a lightweight and easy-to-use Swift package designed to simplify network calls in iOS applications. Built on top of `Alamofire`, this package provides a generic and reusable framework for making REST API calls. Whether you're working on a small project or a large-scale application, MPNetworkPackage can help you manage network requests efficiently.

## Features

- **Generic Network Layer:** Simplifies the process of making API requests by providing a generic network layer.
- **Based on Alamofire:** Leverages the power of `Alamofire`, a popular Swift-based HTTP networking library, for robust and reliable networking.
- **Reusable Components:** Designed to be reusable across different projects, reducing boilerplate code.
- **Error Handling:** Includes built-in error handling for network requests.

## Installation

You can add MPNetworkPackage to your project using Swift Package Manager. To do this:

1. Open your project in Xcode.
2. Go to `File` > `Add Packages...`.
3. In the search bar, enter the URL of this repository.
4. Select the version and add the package to your project.

Alternatively, you can add the following line to your `Package.swift` file:

```swift
dependencies: [
    .package(url: "https://github.com/Noshaid/MPNetworkPackage.git", from: "1.0.0")
]
```

## Usage

### Importing the Package

First, import the package into your Swift file:
```swift
import MPNetworkPackage
```

### Make a Call

Second, make `NetworkManagerProtocol` instance and call `makeCall` method
```swift
let networkManager: NetworkManagerProtocol = NetworkManager()

let url = "YOUR URL STRING"
networkManager.makeCall(withUrl: URL(string: url)!) { (result: Result<YOUR CODABLE MODEL, AFError>) in
    switch result {
        case .success(let obj):
            onSuccess(obj)
        case .failure(let error):
            onFailure(error)
    }
}
```

## Acknowledgments

This package is built on top of the amazing `Alamofire` library. A big thanks to the developers and contributors of `Alamofire` for their excellent work.
