# ScaledCenterCarousel

[![CI Status](http://img.shields.io/travis/yuriy-tolstoguzov/ScaledCenterCarousel.svg?style=flat)](https://travis-ci.org/yuriy-tolstoguzov/ScaledCenterCarousel)
[![Version](https://img.shields.io/cocoapods/v/ScaledCenterCarousel.svg?style=flat)](http://cocoapods.org/pods/ScaledCenterCarousel)
[![License](https://img.shields.io/cocoapods/l/ScaledCenterCarousel.svg?style=flat)](http://cocoapods.org/pods/ScaledCenterCarousel)
[![Platform](https://img.shields.io/cocoapods/p/ScaledCenterCarousel.svg?style=flat)](http://cocoapods.org/pods/ScaledCenterCarousel)

A carousel-based layout for UICollectionView with scaled center item. 
It contains optional paginator to force user to select single item which will be presented exaclty at center of carousel.
Before using library, make sure to have a look at Example project.

![alt tag](https://raw.githubusercontent.com/yuriy-tolstoguzov/ScaledCenterCarousel/master/Example/Assets/ScaledCenterCarousel.gif)

## Example

To run the example project, clone the repo, and run `pod install` from the Example directory first.

## Customization

The library is made purposely simple, but there are number of ways you can customize it. Most of properties could be set from IB via `IBInspectable`.

### Layout

- `centerCellHeight` - The height of cell at the center position.
- `centerCellWidth` - The width of cell at the center position.
- `normalCellHeight` - The height of cells that far enough from the center position.
- `normalCellWidth` - The width of cells that far enough from the center position.
- `proposedContentOffset` - The content offset that will be set once after next data source change. Think about adding items after you get them from web service and you want to pre-select one of them.

### Pagination (UICollectionViewDelegate)

If you want user to be able to select only one item at a time, you probably will use built-in `YTScaledCenterCarouselPaginator` and set it as your `UICollectionView` delegate.

It has next delegate methods:
- `-carousel:didSelectElementAtIndex:`
- `-carousel:didScrollToVisibleCells:`

If your data source will adopt `YTScaledCenterCarouselDataSource` protocol. It will always know what item is selected now and can use this knowledge to add some customization to selected cells. Also it encouraged to check cell selected state, because it's updated accordingly as well.

## Requirements

iOS 7+

## Installation

### [CocoaPods](http://cocoapods.org)

To install
it through [CocoaPods](http://cocoapods.org), simply add the following line to your Podfile:

```ruby
pod "ScaledCenterCarousel"
```

Run update command in your terminal:

```bash
$ pod install
```


### [Carthage](https://github.com/Carthage/Carthage)

Add this line to your Cartfile:

```ruby
github "yuriy-tolstoguzov/ScaledCenterCarousel"
```

Run update command in your terminal:

```bash
$ carthage update
```

## Author

yuriy-tolstoguzov, Yuriy.Tolstoguzov@gmail.com

## License

ScaledCenterCarousel is available under the MIT license. See the LICENSE file for more info.
