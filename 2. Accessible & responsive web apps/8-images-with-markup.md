# Performance
Latency is the new bottleneck.  
->  not only reduce image size but also reduce number of images  

In these lessons: graphical effects without images

# Text problems
Text over images instead of an image with text in it = nicely scalable and less bytes   
Web fonts -> beautiful typography without the need for images   

# CSS techniques  
CSS for shadows, rounded corners, gradients and animations => processing and rendering cost!

# CSS background images
Simple links in notes

# Quiz
```css
background-image: cover;    // completely filles the background
background-image: contain;  // full image is visible
```
# Symbol characters
http://unicode-table.com 

# Unicode treble clef quiz 
Make sure special characters can be shown by adding  
```html 
<meta http-equiv="Content-Type" content ="text/html;charset=utf-8">
```

# Icon fonts
Minimum download + maximum scalability   
All CSS effects can be applied!   
http://css-tricks.com

# Inlining images with SVG and data URIs
SGG: small, scalable, well supported in all browsers   
Data URIs: base64 encoding string  

Can be inlined in CSS as well!  
Why inline? To reduce HTTP requests!
