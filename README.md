LMGeocoder
==============
LMGeocoder is a simple wrapper for geocoding and reverse geocoding dynamically from user input. It is blocked-based geocoder, use both Google Geocoding API and Apple iOS Geocoding Framework.

![](https://raw.github.com/lminhtm/LMGeocoder/master/Screenshots/screenshot.png)

## Features
* Wrapper for Geocoding and Reverse geocoding with blocked-based coding.
* Use both Google Geocoding API and Apple iOS Geocoding Framework.

## Requirements
* iOS 7.0 or higher 
* ARC

## Installation
* Drag the `LMGeocoder` folder into your project.
* Add the <b>CoreLocation.framework</b> to your project.
* Add the -fno-objc-arc compiler flag to SBJson files in Target Settings > Build Phases > Compile Sources.
* Add #include "LMGaugeView.h" to the top of classes that will use it.
* 
## Usage
#### Geocoding
```ObjC
[[LMGeocoder sharedInstance] geocodeAddressString:addressString
                                          service:kLMGeocoderGoogleService
                                completionHandler:^(LMAddress *address, NSError *error) {
                                    if (address && !error) {
                                        NSLog(@"Coordinate: (%f, %f)", address.coordinate.latitude, address.coordinate.longitude);
                                    }
                                    else {
                                        NSLog(@"Error: %@", error.description);
                                    }
                                }];
```

#### Reverse Geocoding
```ObjC
[[LMGeocoder sharedInstance] reverseGeocodeCoordinate:coordinate
                                              service:kLMGeocoderGoogleService
                                    completionHandler:^(LMAddress *address, NSError *error) {
                                        if (address && !error) {
                                            NSLog(@"Address: %@", address.formattedAddress);
                                        }
                                        else {
                                            NSLog(@"Error: %@", error.description);
                                        }
                                    }];
```
See sample Xcode project in `/LMGeocoderDemo`

## License
LMGeocoder is licensed under the terms of the MIT License.

## Say Hi
* [Blog](http://laptrinhiphone.blogspot.com/)
* [Twitter](https://twitter.com/minhluongnguyen)
