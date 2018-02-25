# Starting small

*Dive into the specifics of how pixels on a webpage are rendered and how that impacts the development process.*

Viewport defines the area of the screen the browser can render content to. 
Pixel isn't always a pixel. DIP = device independent pixel. Takes up same amout of space on the display no matter what the number of hardware pixels on the device is. 

If no viewport is defined in the code, the browser takes a shot in serving the content in a good matter, but that doesn't always end up well.
Add the viewport meta to the header of the code.

```html
<meta name="viewport" content="width=device-width,initial-scale=1">
```  

device-width: match the screen width and the DIPs.  
initial scale 1: 1 to 1 relationship between DIPs and CSS pixels. Otherwise problems when rotating and with scaling.

Relative widths are better suited for responsive websites. Exception: images smaller than smallest device don't always need to have relative units.

Catchall recommendation to make sure contents don't get overflowed in CSS:  
```css
img, embed,
object, video {
    max-width: 100%;
}
```

Buttons and input elements should at least be 48px high and wide to make sure they're suitable for tapping with a finger. Also, add at least 40px of room between tap targets to avoid hitting more than one element at the same time.  

The design for a responsive websites starts with the smallest device, usually a phone. When completed, you move on to the next, larger design. At each step you should ask yourself whether it is needed to have another design at this level.  
By starting small, prioritizing content is a must. Consider what absolutely needs to be on the screen for the users. 
By designing for the smallest device first and thinking about the key content that has to be there on each step, performance is being considerated as well #perfmatters  

