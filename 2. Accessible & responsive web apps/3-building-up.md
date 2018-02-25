# Building up

*Learn the most important tools in developing any responsive web application: media queries and flexbox.*

Up until now we've taken a look at individual page elements and how to optimise them for every device. Building a responsive website is more than that. In the following lessons we're taking a step back and look at how to build a repsonsive page.  
Picking the right design pattern can be more of an art than a science. 

A responsive website changes based on the characteristics of the device. It needs to apply different styles when served to different devices. There are different ways to get that done. The easiest way is to use media queries. 

## Three ways of using a media query  
1. as a link  
```css
<link rel="stylesheet" media="screen and (min-width:500px)" href="over500.css">
``` 
2. embed it in the css with @media  
```css
@media screen and (min-width: 500px){
    // css code
}  
``` 
3. import it in the code with @import 
```css
@import url("over500.css") only screen and (min-width: 500px);
```  

Avoid the third (import) method for performance reasons. When using linked or embedded media queries you should keep in mind that linked css files gets you more HTTP requests and smaller files, whereas embedded media queries keep the number of files down, but each of them tends to be bigger.  

Don't use min/max-device width when using media queries. It uses the width of the device and not that of the browser window!

The point at which a page changes layout is called a **breakpoint**. There can be one or several breakpoints in one page, depending on the content and the design.  
Best practice in defining breakpoints is to let the content decide where the breakpoints need to be. Starting small and resizing the window slowly points out where the content needs a change in layout.  

More complex tests in media queries:  
```css
@media screen and (min-width: 500px) and (max-width: 600px){  
    // css code  
}
```   


## Patterns and general strategies  
Gridfluid system: columns end up wrapping to the next line as the browser width gets smaller. (Bootstrap, 960px grid system)  

Flexbox: fills the space available. Elements shrink or expand to use the space available as best as they can.  
```css
.container{
    width: 100%;
    display: flex;
}  
.box {
    width: 150px;
}
```
Flex defaults elements to be on one row, ignoring the width set in the css. The browser resizes all elements so they stay on the same row. That can be changed by adding `flex-wrap: wrap` to the container element.  
```css
.container{
    width: 100%;
    display: flex;
    flex-wrap: wrap;
}  
.box {
    width: 150px;
}
```  

Another feature of using flexbox is the ability of ordering elements using the css order attribute. Combining this with a media query, one can accomplish a design where the elements on the page are positioned elsewhere, based on the device on which the page is viewed.  
```css
@media screen and (min-width: 700px){
    .dark-blue { order: 4; }
    .light-blue { order: 5; }
    .green { order: 2; }
    .orange { order: 3; }
    .red { order: 1; }
}
```

