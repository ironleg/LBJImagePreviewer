# LBJImagePreviewer

`LBJImagePreviewer` is an image previewer implemented with SwiftUI.

## Features

- Zoom with magnification gesture
- Double click to zoom in/out

### Preview

![preview](./preview.gif)

## Installation

`LBJImagePreviewer` can be installed using Swift Package Manager:

1. Copy the package URL: 

```
https://github.com/Lebron1992/LBJImagePreviewer
```

2. Open the menu `File / Add Packages` in Xcode.

3. Paste the URL to the search box and add the library to your project.

## Usage

### `UIImage`

Preview `UIImage`：

```swift
let uiImage = UIImage(named: "lebron")!
LBJUIImagePreviewer(uiImage: uiImage)
```

### `Image`

Preview `Image`：

```swift
// the width/height ratio of `Image` is needed
LBJImagePreviewer(content: Image(uiImage: uiImage), aspectRatio: 2 / 3)
```

### Any `View`

If you don't preview an image with `UIImage` or `Image`, you could preview any `View`. For example, we preview a red background:

```swift
LBJViewZoomer<Color>(content: .red, aspectRatio: 1)
```

### Max Scale

Also you can specify the max scale(`3` by default) when you creating `LBJImagePreviewer`: 

```swift
LBJImagePreviewer(uiImage: uiImage, maxScale: 5)
LBJImagePreviewer(image: Image(uiImage: uiImage), aspectRatio: 2 / 3, maxScale: 5)
```
## Existing Issues

- When you double-click to zoom in, the image can ONLY be zoomed in from the middle, not at the click location. (Currently, we can't set `contentOffset` for `ScrollView` manually, so we have to wait for the `ScrollView` updates to solve the issue.)

## Requesting a Feature

Use GitHub issues to request a feature.