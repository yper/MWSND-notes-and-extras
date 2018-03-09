Pixel Density Descriptor: 1x, 2x...   
```html 
<img src="some.jpg" srcset="some-1x.jpg 1x, some-2x.jpg 2x" >
```

http://pixensity.com <- tables with pixel desity for a number of devices   

Find out in devTools console:
```js
window.devicePixelRatio
```

srcset = make the browser choose the right picture for that very situation.   

# srcset
## Syntax
There are two flavors of srcset, one using x to differentiate between device pixel ratios (DPR), and the other using w to describe the image's width.

### Reacting to Device Pixel Ratio
```html
<img src="image_2x.jpg" srcset="image_2x.jpg 2x, image_1x.jpg 1x" alt="a cool image">
``` 
Set srcset equal to a comma separated string of filename multiplier pairs, where each multiplier must be an integer followed by an x.

For example, 1x represents 1x displays and 2x represents displays with twice the pixel density, like Apple's Retina displays.

The browser will download the image that best corresponds to its DPR .

Also, note that there's a src attribute as a fallback.

### Reacting to Image Width
```html
<img src="image_200.jpg" srcset="image_200.jpg 200w, image_100.jpg 100w" alt="a cool image">
```
Set srcset equal to a comma separated string of filename widthDescriptor pairs, where each widthDescriptor is measured in pixels and must be an integer followed by a w. Here, the widthDescriptor gives the natural width of each image file, which enables the browser to choose the most appropriate image to request, depending on viewport size and DPR. (Without the widthDescriptor, the browser cannot know the width of an image without downloading it!)

Also, note that there's a src attribute as a fallback.