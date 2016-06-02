Two different types of assets
- Images
- Icons


# Images
- Cannot be represented as vector-graphic
- iOS
  * Have to be exported as __.png__ in different scale-factors __(iOS)__
- Android
  * Have to be exported as __.png__ in different scale-factors __(Android)__

## Example

RawImage (300px x 300px)
![](image_example_raw.png)

- Design specifies image should be 44pt x 44pt
- Image should have name `example`


iOS expects:

file-name              | image-size(px) |scale-factor  | example
-----------------------|:--------------:|:------------:|--------
`image_example@1x.png` |44x44           | 1x           | ![](example_ios_image/image_example@1x.png)
`image_example@2x.png` |88x88           | 2x           | ![](example_ios_image/image_example@2x.png)
`image_example@3x.png` |132x132         | 3x           | ![](example_ios_image/image_example@3x.png)

Android expects:

file-name              | image-size(px) |scale-factor  | example
-----------------------|:--------------:|:------------:|--------
`mdpi/example.png`     |44x44           |1x            | ![](example_android_image/mdpi/image_example.png)
`hdpi/example.png`     |88x88           |1,5x          | ![](example_android_image/hdpi/image_example.png)
`xhdpi/example.png`    |132x132         |2x            | ![](example_android_image/xhdpi/image_example.png)
`xxhdpi/example.png`   |132x132         |3x            | ![](example_android_image/xxhdpi/image_example.png)



# Icons
- Can be represented as vector-graphic
- Have to be exported as __.pdf__ @1x __(iOS)__
- Have to be exported in different scale-factors __(Android)__

## Example

RawIcon (300px x 300px)

![](icon_example_raw.png)

- Design specifies image should be 44pt x 44pt
- Icon should have name `example`


iOS expects:

file-name              | image-size(px) |scale-factor  | example
-----------------------|:--------------:|:------------:|--------
`icon_example.pdf`     |44x44           | 1x           | ![](example_android_icon/mdpi/ic_example.png)

Android expects:

file-name             | image-size(px) |scale-factor  | example
-----------------------|:--------------:|:------------:|--------
`mdpi/ic_example.png`     |44x44           |1x            | ![](example_android_icon/mdpi/ic_example.png)
`hdpi/ic_example.png`     |66x66           |1,5x          | ![](example_android_icon/hdpi/ic_example.png)
`xhdpi/ic_example.png`    |88x88         |2x            | ![](example_android_icon/xhdpi/ic_example.png)
`xxhdpi/ic_example.png`   |132x132         |3x            | ![](example_android_icon/xxhdpi/ic_example.png)


# Icon-Tinting
Icons be tinted by specifying the __rendering-mode__ and __tint-color__

- rendering-mode has 2 possible values
  * original (default)
  * template

If rendering-mode = __template__ the original color of the icon is ignored and a new one is applied.


Framework uses the alpha channel of the icon.

```python
for pixel in icon:
  if pixel.alpha > 0
    pixel.color = tint-color
  else
    pixel.color = transparent-color
```



# Example

original-icon: (icon is black)

![](example_icon_tint/icon_raw.png)




tint-color|rendering-mode original| rendering-mode template
----------|-----------------------|:--------------
`black`   |![](example_icon_tint/icon_raw.png)   | ![](example_icon_tint/icon_raw.png)
`blue`    |![](example_icon_tint/icon_raw.png)   | ![](example_icon_tint/icon_blue.png)
`red`     |![](example_icon_tint/icon_raw.png)   | ![](example_icon_tint/icon_red.png)
