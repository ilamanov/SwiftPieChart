# SwiftPieChart

Simple and elegant pie chart for Swift UI

![SwiftUI Pie Chart](./Resources/demo.gif "SwiftUI Pie Chart")

## Usage

```swift
import SwiftPieChart

...

PieChartView(
    values: [1300, 500, 300],
    names: ["Rent", "Transport", "Education"],
    formatter: {value in String(format: "$%.2f", value)})
```

`formatter` is used to format the values for displaying purposes. In the example above we are displaying values with 2 decimal places and with the `$` sign in the front.

## Installation

In Xcode go to `File -> Swift Packages -> Add Package Dependency` and paste in the repo's url: `https://github.com/ilamanov/SwiftPieChart`

## Demo

A demo iOS app shown in the gif above can be found at https://github.com/ilamanov/SwiftPieChartDemo

## Code explanation

## Easy Customization

You can change the width of the pie chart by providing `widthFraction` parameter:
```swift
PieChartView(
    values: [1300, 500, 300],
    names: ["Rent", "Transport", "Education"],
    formatter: {value in String(format: "$%.2f", value)},
    widthFraction: 0.95)
```
![SwiftUI Pie Chart Wider](./Resources/demo_width.png "SwiftUI Pie Chart Wider")

You can change the radius of the inner circle by providing `innerRadiusFraction` parameter:
```swift
PieChartView(
    values: [1300, 500, 300],
    names: ["Rent", "Transport", "Education"],
    formatter: {value in String(format: "$%.2f", value)},
    innerRadiusFraction: 0.5)
```
![SwiftUI Pie Chart Wider Radius](./Resources/demo_radius.png "SwiftUI Pie Chart Wider Radius")

You can change the colors by providing `colors` and `backgroundColor` parameters:
```swift
PieChartView(
    values: [1300, 500, 300],
    names: ["Rent", "Transport", "Education"],
    formatter: {value in String(format: "$%.2f", value)},
    colors: [Color.red, Color.purple, Color.orange],
    backgroundColor: Color(red: 30 / 255, green: 54 / 255, blue: 14 / 255, opacity: 1.0))
```
![SwiftUI Pie Chart Alternate Colors](./Resources/demo_alternate_colors.png "SwiftUI Pie Chart Alternate Colors")

You can provide text color alongside with background color. (textColor is white by default).
Might be helpful when dealing with color schemes.
```swift
struc SomeView: View {
    @Environment(\.colorScheme) var colorScheme

    var body: some View {
        ...
        PieChartView(
            values: [1300, 500, 300],
            names: ["Rent", "Transport", "Education"],
            formatter: {value in String(format: "$%.2f", value)},
            colors: [Color.red, Color.purple, Color.orange],
            backgroundColor: colorScheme == .dark ? .black : .white,
            textColor: colorScheme == .dark ? .white : .black
        )
    }
}
```
![SwiftUI Pie Chart TextColor](./Resources/demo_text_color.png "SwiftUI Pie Chart TextColor")
