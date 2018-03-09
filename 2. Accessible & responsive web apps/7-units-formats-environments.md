Total bits = pixels x bits per pixel  

Window size may change!  
`max-width = 100%` is your friend

```css
width: calc((100% - 10px)/2);  
```

`img:last-of-type` to get last element of the image type and remove right margin for example   

Don't assume viewport size will remain the same!

`vh` = viewport height  
`100vh` = full viewport height   
`vw` exists as well: viewport width  
`vmin` and `vmax` viewport units


For photos use jpg or webp (webp supports transparancy and animation!)  
For other graphical content use svg or png. No gif, png has more colors, better compression and there are no locensing issues.   

PageSpeed Insights checks compression of images.


# Python simple webserver
## Windows 
`py -m http.server`

## Mac
`python -m SimpleHTTPServer`

# Batch convert images
- install Python  
- install grunt-cli  (`npm install -g grunt-cli`)  
- install Image Magick **with legacy tools**  
- `grunt`